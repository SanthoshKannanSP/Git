# Task-8 - Using Git Hooks for Automated Checks
    
## Objectives
- Create a `pre-commit` hook in the `.git/hooks` directory.
- Write a simple script (e.g., a shell script or Node script) that runs a linter or a unit test.
- Ensure that if the tests or linting fail, the commit is aborted.
- Document how Git hooks can improve code quality in collaborative projects.

## Git hooks
Git hooks are scripts that are fired off when certain important actions occur. Hooks allows us to enforce rules, automate tasks and improve workflow in git projects.

## Client-side hooks
Hooks that are run on the local machine either before or after a git action. It is commonly used for code formatting and preventing bad commits. **EG:** `pre-commit`, `commit-msg`

## Server-side hooks
Hooks that are run on the server machine hosting the remote repository before or after a git action. It is commonly used to enforce policies, rejecting bad pushes and logging events. **EG:** `pre-receive`, `post-receive`

## Hook scripts
Hooks scripts can be written in any comfortable scripting language like shell scripts, Python or Node. These scripts have to be properly named and should be placed inside the `.git/hooks` folder of the git repository.
