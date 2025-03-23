# Task-5 - Interactive Rebasing for Clean Commit History

## Objectives
- Create a series of commits (some with minor changes or typos in commit messages)
- Run git rebase -i HEAD~n (with n representing the number of commits) to squash, reorder, and edit commit messages
- Explain how squashing helps in cleaning up commit history before merging into a main branch

## Interactive Rebase
Interractive rebase allows for cleaning up localcommit history. It allows for editing, reordering and squashing commit messages in order to clean up the commit history before pushing to a remote branch.

**NOTE: Interactive Rebase rewrites commit history of the repository. Hence it should only be used in local branches or commits that have not been pushed to the remote yet. Otherwise, it will cause conflicts and other issues for the other developers working on the repository**

## How interactive rebase works
Interactive rebase seperates the specified number of commits and reapplies them one by one, while allowing us to make necessary changes to the commit message and history.

## Performing Interactive Rebase
Use the `git rebase -i` command along with the number of commits to perform rebase on.

```
git rebase -i HEAD~5
```
This will perform rebase on the last 5 commits

Now your git default text editor will open, containing the specified amount of commits. Each line will contain an action keyword, commit hash and commit message. By modifying the action keyword a commit, we can make the necessary changes.

## Action keywords
- pick*(default)* - Keeps the commit as it is
- reword - change the commit message
- edit - pause the rebase to edit this commit
- squash - Merge this commit with the previous one (keeps both messages)
- fixup - Merge this commit with the previous one (keeps only the previous message)
- drop - Delete this commit from history

## Correcting an old commit message
For editing the previous commit message, the `git commit --amend` command can be used. For commits older than that, we have to use interactive rebase.

Start the rebase process,
```
git rebase -i <parent_commit_hash>
```
where *parent_commit_hash* is the commit hash of the parent of the commit we want to edit the commit message of.

In the editor that has just opened, change the action keyword of the commit you want to change the commit message of from pick to reword and close the editor window.

Now another editor window will open with the older commit message. Make the necessary changes to the commit message and close the editor window to finalize it.

## Squashing multiple commits into one
For combining multiple commits into a single one, start the rebase process at atleast the parent commit of the ones we want to squash.
```
git rebase -i <parent_commit_hash>
```

In the editor that has just opened, change the action keyword of the commits you want to combine from pick to reword and close the editor window.
**NOTE: The commit with the squash action keyword will be combined with the commit directly above it in the editor(the previous commit in terms of git history)**

Now another editor window will open with the commit messages of the commits you want to combine. Rewrite the commit message as needed and close the editor window to finalize it.

## Fixing a mistake in a previous commit
In order to fix a mistake made in a older commit, instead of creating another commit to fix the mistakes from the older commit, we can add these changes to the older commit itself using rebase.

Fix the mistake by making necessary changes to the files and stage them. When commiting, use the `--fixup` flag along with the commit hash of the older commit with mistake.

Now start the rebase process at the parent of the commit with mistake, with using the `--autosquash` flag.

In the editor that has just opened, all the necessary changes to add the fix to the older commit with mistake is made by git itself. When we close the window, the fixup will be applied on the older bad commit.

## References
- https://about.gitlab.com/blog/2020/11/23/keep-git-history-clean-with-interactive-rebase/
- https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History
- https://git-scm.com/book/en/v2/Git-Branching-Rebasing
- https://www.youtube.com/watch?v=42392W7SgnE