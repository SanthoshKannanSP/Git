# Task-1 - Initialize, Commit, and Branch Basics
## Objectives
- Initialize a new Git repository
- Create files and commit them
- Creating branch and merging changes

## Installing and configuring Git
Git usually comes pre-installed in most versions of Linux and Mac. If not installed, Git can be installed using the respective package manager of the system.

**Ubuntu**
```sh
sudo apt update
sudo apt install git
```

Before using Git, username and email details have to be configured using `git config` command. These will be the information that are associated with the commits.

```sh
git config --global user.name <username>
git config --global user.email <email>
```

## Initializing a new Git Repository
Any directory can be converted into a git repository using the `git init` command.

```sh
git init
```

When executing the command, Git will create an hidden directory called `.git` in the current directory. This stores all the data that git uses as part of the repository history.

## Adding files to the staging area
In order to add new files or modified files to the git staging area, use the `git add` command. The staging area is an intermediate area where commits can be reviewed and formatted before finalizing them.

- `git add <filename>` - add a new or modified file to the staging area
- `git add .` - add all new or modified file in the current directory to the staging area
- `git add -A` - add all new or modified file in the entire repository to the staging area

## Checking status of the files
To check the status of the files, use the `git status` command.

```sh
git status
```

- Files that are unmodified from previous commit or ignored using `.gitignore` are not shown in the output of `git status`
- Files that are new and not tracked by git yet are shown as *Untracked files*
- Tracked files that are modified, renamed or deleted from the previous commit are shown as *Changes not staged for commit*
- Files that are added to the staging area are shown as *Changes to be committed*

## Commiting the changes
To commit the files in the staging area, use the `git commit` command.

```sh
git commit -m "commit message"
```

The *commit message* is a short description of the changes made as part of a commit.

## Creating branches
Branches allows the creation of seperate lines of developement in the repository. A branch is just a pointer to a specific commit in the repository. This allows developement of multiple features simulataneously without affecting each other or the stable branch.

To create a new branch,
```
git branch <branch_name>
```
This creates a new pointer to the same commit currently on.

**HEAD** is a special pointer that is used to identify the branch currently on.

To switch branches,
```
git checkout <branch_name>
```
This command moves the **HEAD** pointer to the specified branch.

To merge another branch into the current branch,
```
git merge <branch_name>
```

## Checking commit history
To check the commit history of the repository, use the `git log` command.

```
git log
```

## References
- https://git-scm.com/book/en/v2
- https://github.com/git-guides