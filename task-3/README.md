# Task-3 - Undoing Changes and Reverting Commits

## Objective
- Experiment with undoing changes in your working directory and commits

## Unmodifying a modified file
To revert a modified file as in the latest commit, use
```
git restore <file>
```

## Unstage a staged file
To unstage a file added to the staging area using `git add`, use
```
git restore --staged <file>
```

## To revert a commit
To revert the previous commit, use
```
git revert HEAD
```
This will remove the changes introduced as part of the previous commit through a new commit. The new commit is used because simply deleting the previous commit will cause issues if the repo is public and/or worked on by multiple people.

To revert multiple commits, specify the commits in reverse order from latest commit
```
git revert -n HEAD HEAD~1 HEAD~2
```
or specify them using range
```
git revert -n HEAD~2..HEAD
```
This will revert the last three commits. The `-n` flag is used to prevent git from auto-commiting for each revert so that one final commit can be used in the end.

## References
- https://git-scm.com/book/en/v2/Git-Basics-Undoing-Things
- https://www.youtube.com/watch?v=iIaM7j3tMuk
- https://stackoverflow.com/questions/1463340/how-can-i-revert-multiple-git-commits