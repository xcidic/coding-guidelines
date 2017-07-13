---
title: "Setting Up Meanjs Application"
date: 2017-07-13T15:50:10+07:00
draft: false
weight: 5
---

### Setting Up MEANJS Application
- navigate to `YOUR_APP` directory

`cd  /opt/bitnami/apps/YOUR_APP/`

- Get the source

`sudo git clone https://YOUR_GIT_URI/GIT_USERNAME/YOUR_PROJECT_REPO.git htdocs`

- Navigate to source
`cd htdocs`

- Update and Install dependencies

```bash
sudo apt-get update -q
sudo apt-get install -yqq aptitude git traceroute dnsutils tree tcpdump psmisc gcc make build-essential libfreetype6 libfontconfig libkrb5-dev curl
sudo apt-get install -y ruby
sudo gem install sass
sudo npm install --quiet -g grunt-cli gulp bower yo mocha karma-cli pm2 grunt
sudo npm install --quiet --production
sudo bower install --quiet --allow-root --config.interactive=false
```

- Setting up Environment variables

```bash
export NODE_ENV=production
export PORT=3000
export DB_1_PORT_27017_TCP_ADDR=127.0.0.1
export MONGODB_USERNAME=YOUR_DATABASE_USER
export MONGODB_PASSWORD=YOUR_DATABASE_PWD
```

- Backup mongo from `mongolab` (change host, port, username, password and db name)

```bash
mongodump --host YOUR_MLAB_HOST --port YOUR_MLAB_PORT --username YOUR_MLAB_USERNAME --password YOUR_MLAB_USERNAME --db YOUR_MLAB_DB_NAME --excludeCollectionsWithPrefix YOUR_DIRECTORY_DO_NOT_NEED_BACKUP
```

- Restore to your mongodb (change host, port, username, password, db name and path to backup folder)

```bash
mongorestore --host 127.0.0.1:27017 --db YOUR_DB_NAME --username YOUR_DB_USERNAME --password YOUR_DB_PWD dump/YOUR_MLAB_DB_NAME/
```

- Run the NodeJS Server with `pm2`

`pm2 start server.js`

- Restart `Apache` Server

`sudo /opt/bitnami/ctlscript.sh restart`

- If you want to Restart your app with `pm2`

```bash
pm2 list
pm2 restart all
```

- If you want to stop your app with `pm2`

```bash
pm2 list
pm2 stop all
```
