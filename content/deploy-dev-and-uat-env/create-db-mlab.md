---
title: "Create Database on Mlab"
description: ""
date: "2017-04-24T18:36:24+02:00"
weight: 3
---

- Registration using your email

	[Click This Link to Register](https://mlab.com/signup/)

- Click "Create New" to Create new database

![Mlab 1](/coding-guidelines/create-db-mlab/mlab1.png)

- Select Cloud Provider as Google Cloud Platform, Plan Type as SANDBOX and clic "Continue"

![Mlab 2](/coding-guidelines/create-db-mlab/mlab2.png)

- Select the region then click "Continue"

![Mlab 3](/coding-guidelines/create-db-mlab/mlab3.png)

- Set the database name
	- Example database name: 
		- project-a-dev (for development)
		- project-a-uat (for uat)

- Click "Continue" button

![Mlab 4](/coding-guidelines/create-db-mlab/mlab4.png)

- Confirm the order, Click "Submit Order"

![Mlab 5](/coding-guidelines/create-db-mlab/mlab5.png)

- Your database already created

![Mlab 6](/coding-guidelines/create-db-mlab/mlab6.png)

- Click your database to configure the users

![Mlab 7](/coding-guidelines/create-db-mlab/mlab7.png)

- Click "Users" tab, click "Add Database User"

![Mlab 8](/coding-guidelines/create-db-mlab/mlab8.png)

- Set your username add password, then click "Create"

![Mlab 9](/coding-guidelines/create-db-mlab/mlab9.png)

- User has been created

![Mlab 10](/coding-guidelines/create-db-mlab/mlab10.png)

- Backup your local data, go to "cmd"

```bash
mongodump --db YOUR_DB_NAME --excludeCollectionsWithPrefix acl_allows -o YOUR_OUTPUT_DIR
```

- Restore to mongolab

```bash
restore --host YOUR_MLAB_HOST --port YOUR_MLAB_PORT --username YOUR_MLAB_USERNAME --password YOUR_MLAB_USERNAME --db YOUR_MLAB_DB_NAME YOUR_BACKUP_DIR
```

