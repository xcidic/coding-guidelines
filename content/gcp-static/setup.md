---
title: "Setup"
date: 2017-07-13T13:29:54+07:00
draft: false
---

## Hosting Static Web on Google Bucket

- Verify domain ownership eg. www.domain.com

- https://www.google.com/webmasters/verification/home

- Follow the instruction to add DNS TXT Record

- And add CNAME for target with “c.storage.googleapis.com”

- After domain verified, add new Google Storage Bucket with the name of domain www.domain.com

- Edit website configuration

![GCP Static](/coding-guidelines/gcp-static/gcp-static1.png)

- For uploading to Google Storage Bucket please install Google Cloud SDK by this instruction

	[Click This Link to See Insturction](https://cloud.google.com/storage/docs/gsutil_install)

- On the build folder project do uploading your static web by executing gsutil command

	`gsutil -m -h "Cache-Control:public, max-age=604800" cp -z js,html,css -a public-read * gs://www.domain.com`

	- Detail:

		- -m for multiple upload

		- -h "Cache-Control:public, max-age=604800" for set cache control

		- cp for copying

		- -z js,html,css for set gzip compression on js html and css

		- -a public-read set access public read

		- gs://www.domain.com

- Wait until finish.

- Done