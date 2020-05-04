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

### Creating a Repository from Scratch

### Staging Files

### Commiting Files

### Checking Older Versions

### 

## Using Hosted Remote Repositories

### Setting Up a Repository on Github/Gitlab

### Pushing/Pulling from/to Remotes
