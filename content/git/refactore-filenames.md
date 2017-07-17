---
title: "Refactor filenames"
date: 2017-07-14T10:59:35+07:00
draft: false
weight: 6
---

## Refactor filenames

  - Deletes the file from the working directory and stages the deletion
  
    `git rm [file]`
    
  - Removes the file from version control but preserves the file locally
  
    `git rm –cached [file]`
    
  - Changes the file name and prepares it for commit
  
    `git mv [file-original] [file-renamed]`
    