# Feature Toggles

## Background

> Feature Toggles (often also refered to as Feature Flags) are a powerful technique, allowing teams to modify system behavior without changing code. They fall into various usage categories, and it's important to take that categorization into account when implementing and managing toggles. Toggles introduce complexity. We can keep that complexity in check by using smart toggle implementation practices and appropriate tools to manage our toggle configuration, but we should also aim to constrain the number of toggles in our system.
>
> *From https://martinfowler.com/articles/feature-toggles.html*

The article above describes four types of feature toggles, which vary on the axes of longevity and dynamism.

1. Release Toggles - Used for enabling trunk-based development for teams practicing Continuous Delivery. This allows the team to check-in code that may not be ready to deploy yet, without maintaining long-living Git branches.
2. Experiment Toggles - Used for performing A/B testing.
3. Ops Toggles - Used for things that may impact performance, etc and may want to sometimes be turned off to preserve stability.
4. Permissioning Toggles - Used for turning features on only for certain users.

Right now, we are primarily concerned with Release Toggles and Permissioning Toggles. Here are some examples from the wild:

### Example 1

Intake has an environment variable for whether to include only Clients in Snapshot searches or all People from CWS/CMS. This was a feature that we wanted to try out without having to deploy new code through the pipeline. It was a small code path change, so introducing a flag based on an environment variable was not intrusive.

### Example 2

Ferb has an environment variable controlling its preloaded system code cache. This was a feature that we thought would be beneficial, but there were still some questions about performance impact or other side effects. Being able to turn it off with an environment variable provided a failsafe in case things went awry.

This may sound like an Ops Toggle, but it is actually more of a Release Toggle. The feature, once proven stable, was intended to be turned on everywhere, at which point the toggle could be removed.

## Release Toggles

The most common type of feature toggle we expect to see is a Release Toggle, which is a short-lived, statically configured toggle that maintains the ability to merge unfinished code or features into the main Git trunk without blocking Continuous Delivery.

### When to Use a Release Toggle

* When you are developing a feature or functionality that will take a long time to develop. Maintaining a large PR branch, especially across sprint boundaries, is painful; merging large branches can introduce conflicts that are hard to resolve or which easily introduce bugs.
* A Product Owner may decide to hold back a larger set of functionality until several pieces are ready. Even if each piece is deployable independently, waiting for the full set to be ready could be the best user experience.
* Do not use a Release Toggle for long-standing branches in functionality. Release Toggles should have a well-defined timeline, after which the feature they protect has been released and the toggle can be removed. This helps keep down the complexity associated with toggle proliferation.

### How to create a Release Toggle

The current approach to configuring a Release Toggle is through de-ansible. Create a variable in de-ansible that can then control the presence of an Environment Variable or command line argument.

Future work may look into configuring release toggles through a more sophisticated system such as Zookeeper.

## Permissioning Toggles

Permissioning Toggles control who can see which feature, typically at a user-by-user level. This can allow for testing of unreleased functionality by internal users.

### When to Use a Permissioning Toggle

* When you have a Release Toggle that is ready to go, but you do not want to release it to all users at once, you can convert it to a Permissioning Toggle.
* When you have a long-standing chunk of functionality that will not be released to users for a while, but you want to test it internally throughout all environments. (Ex: `Hotline-rollout`)

### How to create a Permissioning Toggle

The current approach to configuring a Permissioning Toggle is to create a privilege in Cognito, which the application will receive from Perry. There are a handful of existing 'umbrella' privileges, such as `development-not-in-use` or `Hotline-rollout` that may encompass multiple features. Consider whether or not your permissioning toggle should be controlled separately from or together with an existing toggle.

## Implementation Guidelines

Toggles can be incredibly useful, but they also increase complexity. To help keep the carrying cost of toggles low, consider the following tips:

1. When you create a Release Toggle, it should have a short lifespan. Consider creating a Jira story immediately, marked for the fix version where you expect the Toggle to be removed.
2. Consider naming toggles with a standard naming convention, like `feature_{some feature}`, so that it is easy to separate them from other environment variables in de-ansible or privileges in Cognito.
3. Read some of the tips in [The Martin Fowler article](https://martinfowler.com/articles/feature-toggles.html) for keeping code with toggles maintainable.

## Further Reading

1. [Martin Fowler article](https://martinfowler.com/articles/feature-toggles.html), written by Pete Hodgson
2. http://featureflags.io
