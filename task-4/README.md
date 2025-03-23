# Task-4 - Simulating and Resolving Merge Conflicts

## Objectives
- Create two branches from the same commit
- Modify the same line(s) of code in a common file in both branches.
- Attempt to merge the branches, observe the conflict, and resolve it manually

## Merge conflicts
Merge conflicts arise when branches with competing commits are merged. Usually merge conflicts arise when different changes are made to the same line of the same files or one person edits the file while other deletes the same file. These merge conflicts have to be resolved before finalizing the merge through a commit.

## Resolving merge conflicts
In order to view the files which are affected by merge conflicts use `git status`

After identifying the affected files, open them in a text editor like VS Code to resolve the conflicts.

**Format of a merge conflict**
```
<<<<<< HEAD
<commit in HEAD>
=======
<commit in branch-a>
>>>>>> branch-a
```
Delete the conflict markes `<<<<<<<`, `=======` and `>>>>>>>` and make the changes that should be part of the final merge.

## Finalizing merge
After resolving all the merge conflicts, finalize the merge by staging the changes and commiting it.
```
git add .
git commit -m "Resolve merge conflict"
```

## References
- https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/addressing-merge-conflicts/about-merge-conflicts
- https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/addressing-merge-conflicts/resolving-a-merge-conflict-using-the-command-line
- https://www.youtube.com/watch?v=Sqsz1-o7nXk