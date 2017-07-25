---
title: "Setting Environment Variable"
description: ""
date: "2017-04-24T18:36:24+02:00"
weight: 5
---

- Login to your Heroku

	[Click This Link to Login](https://id.heroku.com/login)

- Select your apps

![Env 1](/coding-guidelines/setting-env-variable/env1.png)

- Go to Settings menu

![Env 2](/coding-guidelines/setting-env-variable/env2.png)

- Click "Reveal Config Vars" Button

![Env 3](/coding-guidelines/setting-env-variable/env3.png)

- Fill the key field and value field then click "Add" button

![Env 4](/coding-guidelines/setting-env-variable/env4.png)

- From that list, at least you input:
	- ADMIN EMAIL: fill with the admin email
	- DOMAIN: fill with your heroku domain
	- MAILER_EMAIL_ID: your account mailer
	- MAILER_FROM: your account mailer
	- MAILER_PASSWORD: your password
	- MAILER_SERVICE_PROVIDER: your smtp service
	- MONGOLAB_URI: your mongodb URI (mongodb://<dbuser>:<dbpassword>@ds147872.mlab.com:47872/project-a-dev)

- You can get mongodb uri on your mongolab
![Env 5](/coding-guidelines/setting-env-variable/env5.png)

- Restart your heroku

```bash
heroku restart
```