---
title: "Setting Up Mongodb"
date: 2017-07-13T15:48:25+07:00
draft: false
weight: 4
---

### Setting Up MongoDB

- Login to mongodb, your password is on dashboard

`$ mongo admin --username root --password YOUR_DB_PWD`

- Create new database name

`use YOUR_DB_NAME`

- Create new User for that DB

```javascript
db.createUser( { user: "YOUR_database_user", pwd: "YOUR_database_password", roles: [ "readWrite", "dbAdmin" ]} )
```
