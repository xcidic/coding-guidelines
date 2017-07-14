---
title: "Suppress tracking"
date: 2017-07-14T10:59:35+07:00
draft: false
weight: 7
---

## Suppress tracking

  * .gitignore

  	* *.log
  	
  	* build/
  	
  	* temp-*
  	
  	* A text file named .gitignore suppresses accidental versioning of files and paths matching the specified patterns


  - Lists all ignored files in this project

  	`git ls-files –other –ignored –exclude-standard`