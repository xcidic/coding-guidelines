---
title: "Synchronize changes"
date: 2017-07-14T10:59:35+07:00
draft: false
weight: 7
---

## Synchronize changes

  - Downloads all history from the repository bookmark
  
    `git fetch [bookmark]`
    
  - Update history of remote branches, you can fetch and purge
  
    `git fetch -p`
    
  - Combines bookmark's branch into current local branch
  
    `git merge [bookmark]/[branch]`
    
  - Push current branch to remote branch
  
    `git push`
    
  - Manually specify remote and branch to use every time
  
    `git push [remote] [branch]`
    
  - If a remote branch is not set up as an upstream, you can make it so
  
    `git push -u origin master`
    
  - Downloads bookmark history and incorporates changes
  
    `git pull`
    
  - Specify to pull a specific branch
  
    `git pull [remote] [branch]`
    
  - See list of remote repos available
  
    `git remote`
    
  - Detailed view of remote repos available
  
    `git remote -v`
    
  - Add a new remote
  
    `git remote add [remote] [url]`
    
