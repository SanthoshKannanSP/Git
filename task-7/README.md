# Task-7 - Cherry-Picking Commits Between Branches

## Objectives
- Create two branches with distinct commits
- Identify a commit on one branch that you want to apply to the other
- Use git cherry-pick <commit-hash> to apply the commit and handle any conflicts if they arise
- Verify the commit history to ensure the cherry-picked commit is present

## Chery-pick
`cherry-pick` command allows for applying specific commits from other branches into the current branch. This is different from `merge` where all the changes in another branch are added to the current branch and `rebase` which moves all the commits in another branch to the HEAD of the current branch.

`Cherry-pick` allows us the selectively apply needed changes from other branches, such as bug fixes, into the current branch without applying any unnecessary commits that are present in the other branch.

## Getting the commit hash from the other branch
Use `git log <branch>` to get the commits and their hashes from the other branch.
```
git log <branch> --oneline
```

After finding and copying the commit hash of the necessary commit, apply that commit to the current branch using `cherry-pick`
```
git cherry-pick <commit_hash>
```

## References
- https://git-scm.com/docs/git-cherry-pick
- https://www.youtube.com/watch?v=i657Bg_HAWI

