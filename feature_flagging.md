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
