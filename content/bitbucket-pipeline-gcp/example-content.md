---
title: "Example Content"
date: 2017-09-27T14:52:47+07:00
draft: false
weight: 4
---

### Example Content

![SSH Keys](/coding-guidelines/bitbucket-pipeline/example.png)

- The image is docker image you are using, in this example I’m using docker image built by dpolyakov (https://hub.docker.com/r/dpolyakov/docker-node-latest-with-rsync/) If you want specific build image just created your self.

- The pipelines is contain step by step to build and deploy your source code,
Cache meaning we cache node and node_modules so we reduce the time for installing node modules.

- In script we put step by step to install your source code, this step is different each framework, you can also do integration testing or tdd test in this script.

- Rsync is tools to copy the result of build to remote server. (https://en.wikipedia.org/wiki/Rsync)

- The ssh command is to stop/start/restart the service inside remote server.


