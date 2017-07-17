---
title: "Make Changes"
date: 2017-07-14T10:59:35+07:00
draft: false
weight: 4
---

## Make Changes
  - Lists all new or modified files to be committed

    `git status`

  - Short view of status

    `git status -s`

  - Shows file differences not yet staged

    `git diff`

  - Snapshots the file in preparation for versioning

    `git add [file]`

  - Add all modified files to be commited

    `git add .`

  - Add only certain files

    `git add '*.txt'`

  - Snapshot only chunks of a file

    `git add –patch filename.x (or -p for short)`

  - Tell git not to track the file anymore

    `git rm [file]`

  - Show what has been added to the index via git add but not yet committed

    `git diff --cached`

  - Shows what has changed since the last commit.

    `git diff HEAD`

  - Shows what has changed since the commit before the latest commit

    `git diff HEAD^`

  - Compare current branch to some other branch

    `git diff [branch]`

  - Same as diff, but opens changes via difftool that you have configured

    `git difftool -d`

  - See only changes made in the current branch

    `git difftool -d master..`

  - See only the file names that has changed in current branch

    `git diff –no-commit-id –name-only –no-merges origin/master…`

  - See statistics on what files have changed and how

    `git diff –stat`

  - Unstages the file, but preserves its contents

    `git reset [file]`

  - Record changes to git. Default editor will open for a commit message

    `git commit`

  - Records file snapshots permanently in version history

    `git commit -m "[descriptive message]"`

  - Change the history, editing the HEAD commit

    `git commit –amend`

  - Change the history, editing a specific commit other than HEAD

    `git commit --fixup=[sha]; git rebase -i --autosquash`

  - Change the history, reword/edit/squash/fix a group of latest commits

    `git rebase -i HEAD~5`
