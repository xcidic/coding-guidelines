---
title: "Configuring Apache"
date: 2017-07-13T14:52:47+07:00
draft: false
weight: 3
---

### Configuring Apache

- Default Installation Directory `/opt/bitnami`
- Start the service

    `sudo /opt/bitnami/ctlscript.sh start`

- Create the directories (below this, change YOUR_APP to your app name)

  ```bash
  sudo mkdir /opt/bitnami/apps/YOUR_APP
  sudo mkdir 	/opt/bitnami/apps/YOUR_APP/conf
  sudo mkdir /opt/bitnami/apps/YOUR_APP/htdocs
  ```

- Create `httpd-prefix.conf` config file

  ```bash
  sudo touch /opt/bitnami/apps/YOUR_APP/conf/httpd-prefix.conf
  sudo vim /opt/bitnami/apps/YOUR_APP/conf/httpd-prefix.conf
  ```

- Insert the following to `httpd-prefix.conf` then save
`Include "/opt/bitnami/apps/YOUR_APP/conf/httpd-app.conf`

- Create `httpd-app.conf` config file

  ```bash
  sudo touch /opt/bitnami/apps/YOUR_APP/conf/httpd-app.conf
  sudo vim /opt/bitnami/apps/YOUR_APP/conf/httpd-app.conf
  ```

- Insert the following to `httpd-app.conf` then save

  ```bash
  ProxyPass / http://127.0.0.1:3000/
  ProxyPassReverse / http://127.0.0.1:3000/
  ```

- Edit Apache configuration

`sudo vim /opt/bitnami/apache2/conf/bitnami/bitnami-apps-prefix.conf`

- Add the following to end of line

`Include "/opt/bitnami/apps/YOUR_APP/conf/httpd-prefix.conf"`
