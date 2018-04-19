# Branching strategy

The existent GitHub - JIRA integration requires our branching strategy to be consistent.
The structure of branch names should be:

```<JIRA User Story Id>-<Story-title-separated-by-dashes>```

Examples:

```
  INT-120-Fix-search-results-duplication
  INT-239-Remove-quotes-around-phone-number
```

# Commit messages

JIRA also tracks commits that contain the User Story ID on them.
That can be added manually like:

```git-commit -m "CALS-123 Installed Redux npm package"```

Another option is to have a git hook that can do it for us.
Adding the following code to `.git/hooks/pre-commit-message`

```
#!/bin/bash
# Include any branches for which you wish to disable this script
if [ -z "$BRANCHES_TO_SKIP" ]; then
  BRANCHES_TO_SKIP=(master develop staging test)
fi
# Get the current branch name and check if it is excluded
BRANCH_NAME=$(git symbolic-ref --short HEAD)
BRANCH_EXCLUDED=$(printf "%s\n" "${BRANCHES_TO_SKIP[@]}" | grep -c "^$BRANCH_NAME$")
# Trim it down to get the parts we're interested in
TRIMMED=$(echo $BRANCH_NAME | sed -e 's:^\([^-]*-[^-]*\)-.*:\1:' -e \
    'y/abcdefghijklmnopqrstuvwxyz/ABCDEFGHIJKLMNOPQRSTUVWXYZ/')
# If it isn't excluded, preprend the trimmed branch identifier to the given message
if [ -n "$BRANCH_NAME" ] &&  ! [[ $BRANCH_EXCLUDED -eq 1 ]]; then
  sed -i.bak -e "1s/^/$TRIMMED /" $1
fi
```

This code will prepend the User Story Id to all commit messages.

