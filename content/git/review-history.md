---
title: "Review history"
date: 2017-07-14T10:59:35+07:00
draft: false
weight: 7
---

## Review history

  - Lists version history for the current branch

	`git log`

  - Lists version history for a file, including renames

	`git log –follow [file]`

  - Pretty commit view, you can customize it as much as you want

	`git log –pretty=format:"%h %s" –graph`

  - See what the author has worked on in the last week

	`git log –author='Name' –after={1.week.ago} –pretty=oneline –abbrev-commit`

  - See only changes in this branch

	`git log ––no-merges master..`

  - Shows content differences between two branches

	`git diff [file-branch]…[second-branch]`

  - Outputs metadata and content changes of the specified commit

	`git show [commit]`

  - Check sha1/unique name of HEAD commit

	`git rev-parse --short HEAD`

