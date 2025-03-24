# Task-9 - Working with Remote Repositories and Collaboration

- Create a local repository and push it to a remote service (e.g., GitHub or GitLab).
- Create a feature branch, make commits, and push the branch to the remote.
- Open a Pull Request (or Merge Request) and perform a code review process.
- Merge the feature branch into the main branch on the remote and then pull the changes locally.

## Remote repositories
Remote repositories are Git repositories hosted over the internet or a network. This allows multiple people to collab on the same project by pushing and pulling changes from the remote repository.

## Listing the remote servers
To list the remote servers that have been configured to the current repository, use `git remote` command. This will list the remotes as shortnames that is used by Git inplace of the actual URLs of the remote. To get the actual URLs that are used when reading and writing to the remotes, use `-v` flag.

## Adding a remote
To add a remote repository to the local repository, use
```
git remote add <remote_name> <repository_url>
```
where `remote_name` is the shortname to identify the remote repository and `repository_url` is the URL of the remote repository.

## Cloned repository
If the local repository is cloned from a remote repository, then Git automatically sets a remote with shortname `origin` with the URL of the remote repository.

## Common remote repository services
- GitHub
- GitLab
- Bitbucket

## Pulling from remotes
Once the remote has been set, `git fetch` command can be used to get the data from the remote repository.
```
git fetch <remote>
```
This will get the data that the local repository doesn't have from the remote repository yet. However, `fetch` command only downloads the data to the local repository and doesn't automatically merge it with the working directory. So one has to manually merge it with the local work.

The `git pull` command both fetches the data from the remote repository and merges it with the working directory by modifying the local files. However, if there are any modified tracked files in the working directory that conflicts with the remote repository, the merge task will abort and only the local repository will be updated.

## Pushing to remotes
Once the remote has been set, `git push` command can be used to push all commits from the local repository to the remote repository.
```
git push <remote> <branch>
```

However, if the local repository is behind the remote repository, the push will be rejected. The new changes have to be fetched from the remote repository and merged with the working directory before you can push the commits.

## References
- https://git-scm.com/book/ms/v2/Git-Basics-Working-with-Remotes
- https://about.gitlab.com/blog/2024/09/24/git-pull-vs-git-fetch-whats-the-difference/