# Task-6 - Stashing Changes for Context Switching

## Objectives
- Make changes in your working directory without committing
- Use git stash to save these changes
- Switch branches, perform some work, then return and reapply your stashed changes with git stash pop
- Optionally, demonstrate how to view and manage multiple stashes using git stash list and git stash drop

## Stashes
Stashing allows saving any modified tracked files and staged changes onto a stack. After stashing, the working directory will be clean with no changes from the previous commit. This is useful when we need to switch branches, as git will not allow switching branches when there are uncommited changes.

```
git stash
```

By default, stash only pushes tracked and stages files into the stack. To push untracked files also, use the `--include-untracked` or `-u` flag.
```
git stash --include-untracked
```

The above command will not include the explicitly ignored files, such as files mentioned in `.gitignore`. To include ignored files also, use the `--all` or `-a` flag.
```
git stash -a
```

## Listing the stashes in the stack
To view all the stashes that are present in the stack use,
```
git stash list
```

## Applying stash
In order reapply the files in the stash to the working directory, use
```
git stash apply
```

This will apply the last stash pushes onto the stack to the working directory. To apply the stash at a specific index use,
```
git stash apply stash@{<index>}
```

## Removing stash from stack
`apply` will not deleted the stash from the stack and will only apply it to the working directory. To remove the stash at a specific index use,
```
git stash drop stash@{<index>}
```

In order to apply and drop the stash at the same time use,
```
git stash pop stash@{<index>}
```

## References
- https://git-scm.com/book/en/v2/Git-Tools-Stashing-and-Cleaning