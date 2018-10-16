# Feature Flags

## Initial Notes

Every application should have some way of blocking off an experimental feature
or unstable block of code, based on an environment variable in de-ansible.
Changing an environment variable is much faster than deploying a new version of
the application through all environments, especially when the target
environment is Staging or beyond.

Example 1: Intake has an environment variable for whether to include only
Clients in Snapshot searches or all People from CWS/CMS. This was a feature
that we wanted to try out without having to deploy new code through the
pipeline. It was a small code path change, so introducing a flag based on an
environment variable was not intrusive.

Example 2: Ferb has an environment variable controlling its preloaded system
code cache. This was a feature that we thought would be beneficial, but there
were still some questions about performance impact or other side effects.
Being able to turn it off with an environment variable provided a failsafe in
case things went awry.

Managing environment variables is mostly manual right now, and they do have to
be remembered to be set for initial deployments. So, adding a flag for every
little feature might become too unwieldy; just be aware that it is in your toolbox if you need it.

## More Initial Notes

1. All code that is merge will eventually, by default, flow to production.
(This is not hypothetical; we have code in production and will be pushing
more, frequently.)
2. Because of (1), developers must only merge stable code. If something is
broken, roll it back.
3. If you have a large feature that is experimental or unstable, you can hide
it behind an environment variable so that we can merge it and test it while
still remaining flexible to roll *other* work out to Staging and beyond.

## Notes from Senior Dev discussion

In discussing with the Senior Dev meeting, several points were raised. These
should each be investigated.

1. Our current method of managing environment variables is very manual, through
de-ansible. There may be tools such as Zookeeper which could help with this.
2. Some teams may not be clear on how to create an environment variable.
3. Some projects, like Perry, already have a lot of environment variables.
With more variables comes more complexity, rarely used code branches are
not usually thoroughly tested, and combinations of variables do not always work
well together.
4. We have some privileges, like Hotline-rollout or development-not-in-use,
that we can also use to guard features. What role (no pun intended) do these
play in the big picture of feature flagging?
