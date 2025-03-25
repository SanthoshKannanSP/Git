# Comprehensive Workflow with Forced Pushes and Recovery

## Objectives
- Create a repository with multiple branches representing features, bug fixes, and releases.
- Simulate a scenario where a forced push (git push --force) is required (for example, after rewriting history with an interactive rebase).
- Use `git reflog` to locate and recover lost commits after a mistaken force push.
- Document each step, explaining how and why forced pushes should be handled with care, and how git reflog can be a lifesaver
- Discuss best practices for collaborating with teams when rewriting history and using force pushes

## Reflog
Git maintains a reference log or reflog of where the HEAD and branch references have been in the local repository as you make changes. This reflog can be viewed using the `git reflog` command. Whenever a branch tip is updated, it is recorded in the reflog. However, this reflog is stricly local to the local repository and will not be pushed to the remote repository. Hence, if the project is just cloned, it will have a empty reflog.

## Recovering Lost Commits
If a commit has been lost due to a rebase and forced push, `git reflog` can be used to recover the lost commits using the hash of the lost commits. After finding the lost commit, either the working directory can be forced reset to the lost commit or a new recovery branch can be created from the lost commit.

## Recovering a deleted branch
Suppose if a branch has been deleted, but it had some important commits that have not been merged, the branch can be recovered using `git reflog` by creating a new branch from the last known commit of the deleted branch.

## Handling Forced Push
Forced push is a destructive operation that replaces the remote branch's history with the local history, potentially erasing commits made by others. This can cause conflicts, loss of work, and distruption.

## Best practices when using force pushes
- The `--force-with-lease` flag can be used instead of `--force` flag, which prevents the push if the remote branch has any new commits that you haven't seen
- Communicating with the collaborators before the force push to ensure everyone is updated and can work around the force push without issue

## References
- https://git-scm.com/docs/git-reflog
- https://github.blog/open-source/git/how-to-undo-almost-anything-with-git/