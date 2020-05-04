# Git Workflow

This document is meant as an internal tutorial for Git, and most parts are taken
from other pages. No guarantees. For an excellent reference see [Scott Chacon's book](https://git-scm.com/book/en/v2).

## What is Git?
Git is a distributed version-control system for tracking changes in source code during software development.

## Basic Concepts of Git
Possible status of files in a version-controlled folder:
- Untracked: a file that is not version controlled
- Unmodified: a version controlled file without changes
- Modified: a version controlled file with changes
- Staged: a changed or new file to be commited

Their relationships are demonstrated in the figure below: ![LifeCycle](lifecycle.png)

In Git commits are organized into a tree, based on their relationships.
As any real tree, a commit tree can also have branches which makes possible
the divergence of project, and allows us to separately work on it. The
labels associated with parts of the branch are actually lightweight pointers
similar to the pointers in C. As a consequence, they can efficiently be moved,
renamed or deleted.
* commit hash: an SHA-1 of the commit along with the author’s name, email, the date written, and the commit message
(consists of 40 charachters, but usually the first few (6) are enough to identify a commit)
* master branch: customary name of the "main" branch
* tag: a fixed pointer to a specific commit (similar to a branch, but fixed)
* HEAD: the "current branch" the user is looking at
![Branching](branch-and-history.png)

## Working Locally

### First-time Setup
Git needs to know your name and email address, as these are baked into every comment. Based on this, other users know who to turn to in case they have an issue (or they `git blame` you):
``` bash
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
git config --global core.editor vim
# git supports aliases
git config --global alias.co checkout
```

### Creating a Repository from Scratch
You can create a new git repository by typing:
``` bash
cd /path/to/your/existing/code
git init

# or alternatively
git init <project directory>
```

### Staging Files
When you finish a logical chunk of your work, you can create a new commit. There are many options to handcraft a commit, using the main tool `git add`. Adding a file moves it into the staging are. This means that the file is flagged to be committed in the next commit. You can view the current status of the files using `git status`
``` bash
git add filename

# add only parts of a file. The rest is kept unstaged or modified
git add --patch filename

# oops! You've added something that you did not mean to...
git reset <file>
# ...or you can "un-add" all:
git reset

# now, let's see what's up with our files
git status
```

### Commiting Files
Now that you managed to perfectly tailor the files in the next commit, you can `git commit` them:
``` bash
# typing the following launches your text editor. Here, its vim.
# you can type your commit message there. The first line should
# be a short summary, followed by an empty line and then a more
# verbose description of the changes.
git commit

# only want a short commit message?
git commit -m "Short commit message"

# darn, messed up the commit message, and left a file out...
git add missing_file
git commit --amend
```

### Checking Older Versions
Awesome! We have some commits in our project, and we can navigate between them. This way, we can check
what was changed between versions (or commits). The simplest way to print the commit tree is `git log`:
``` bash
git log

# or a nicer version with other branches visible, too
git log --all --decorate --graph

# oh, that was a mouthful! Let's alias it!
git config --global alias.longlog=log --all --decorate --graph
```

### Setting Up and Navigating Between Branches

## Using Hosted Remote Repositories

### Setting Up a Repository on Github/Gitlab

### Pushing/Pulling from/to Remotes
