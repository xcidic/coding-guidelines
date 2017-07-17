---
title: "Group changes"
date: 2017-07-14T10:59:35+07:00
draft: false
weight: 5
---

## Group changes

  - Lists all local branches in the current directory

	`git branch`

  - Create a new branch

	`git branch [branch-name]`

  - Switches to the specified branch and updates the working directory

	`git checkout [branch-name]`

  - Switches to a remote branch

	`git checkout -b <name> <remote>/<branch>`

  - Return file to it's previous version, if it hasn’t been staged yet

	`git checkout [filename]`

  - Combines the specified branch's history into the current branch

	`git merge [branch]`

  - Merge branch without fast forwarding

  	`git merge –no–ff [branch]`

  - See the full list of local and remote branches

  	`git branch -a`

  - Deletes the specified branch

  	`git branch -d [branch]`

  - Hard branch delete, will not complain

  	`git branch -D [branch]`

  - Rename a branchgit branch -m <oldname> <newname>

  	`git branch -m <oldname> <newname>`
