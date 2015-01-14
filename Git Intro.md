## Git Intro

#### Configuration

* `git config --global user.name "John Doe"`
* `git config --global user.email name@domain.com`
* `git config --global color.ui auto`

#### Initialization

*Creating a brand new project?*

1. `git init` in a folder you want to add version control to
2. Create a repository for this project on GitHub
3. `git remote add`, with a remote name (conventionally, "origin") and the GitHub repo URL

*Cloning an existing project?*

`git clone` and the URL of the project you're cloning

#### Simple Workflow

1. Make changes to files

2. `git status` to see files changed
3. `git diff` to see specific lines changed
4. `git add` files to "staged" status
5. `git commit` to create a checkpoint (with message)
6. `git push` to update remote repo to current state

#### Branches

We'll talk a lot more about branches later on. For now, here's what we need to understand conceptually.

* Git creates a timeline of commits called a "tree"; all commits are part of a branch of that tree
* When a branch is created, any file changes made on the branch are kept separate from any file changes made on the trunk
* A branch's changes can be merged back into the trunk (we'll worry about how later)

*Creating a new branch*

`git branch new_branch_name`

*Changing from one branch to another*

`git checkout destination_branch_name`

#### Other Commands

* `git log` - shows commits and messages
* `git checkout` - also does...
    * Reset changes made to *unstaged* file
    * Change files to a specific commit
* `git tag` - creates named checkpoint for easy return
