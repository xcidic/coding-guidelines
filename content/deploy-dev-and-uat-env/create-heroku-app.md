---
title: "Create Heroku App and Deploy"
description: ""
date: "2017-04-24T18:36:24+02:00"
weight: 3
---

## Creating Heroku App and Deploy

- Open "cmd" or "Terminal"

- Login heroku using your heroku user
  ```bash
  $ heroku login
	Enter your Heroku credentials.
	Email: adam@example.com
	Password (typing will be hidden):
	Authentication successful.
  ```
	

- Go to you project directory and create app on heroku
  -	Application Name:

		1. Development: project-name-dev

		2. UAT: project-name-uat

  ```bash
  $ heroku create application-name
  Creating app... done, ⬢ sleepy-meadow-81798
  https://sleepy-meadow-81798.herokuapp.com/ | https://git.heroku.com/sleepy-meadow-81798.git
  ```
- Set your remote repository

  ```bash
  $ heroku git:remote -a falling-wind-1624
  Git remote heroku added.
  ```

- Build code use grunt

  ```bash
  $ grunt build --force
  ```

- Deploy your code
  - Default deploy

  ```bash
  $ git push heroku master
	Initializing repository, done.
	updating 'refs/heads/master'
	...
  ```
  Branches pushed to Heroku other than master will be ignored by this command. If you’re working out of another branch locally, you can either merge to master before pushing, or specify that you want to push your local branch to a remote master. To push a branch other than master, use this syntax:

  ```bash
  $ git push heroku yourbranch:master
  ```
