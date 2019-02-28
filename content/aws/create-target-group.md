---
title: "Create Target Group"
date: 2018-11-21T14:00:00+07:00
draft: false
weight: 4
---

### 1. Choose EC2
After Sign In success, click menu "Service" on header, then click "EC2".

![SSH Keys](/coding-guidelines/aws/aws-service.png)

### 2. Create Target Group
Click "Target Groups" on left menu, then click "Create Target Group" button to create a new target group.

![SSH Keys](/coding-guidelines/aws/aws-tg-1.png)

### 3. Key In Target Group Name
We create a new target group, the name depends the project name. If the project name is **"Project Sample Staging Backend"**, so the target group name is **"project-sample-staging-backend"**. Then click "Create" button.

![SSH Keys](/coding-guidelines/aws/aws-tg-2.png)

### 3. Edit Target of Target Groups
We select our new target group. On bottom menu, select "Targets" tab, then click "Edit" button.

![SSH Keys](/coding-guidelines/aws/aws-tg-3.png)

### 4. Add Instance to registered
We select our instance and key in the project port. Then, click "Add to Registered" button.

![SSH Keys](/coding-guidelines/aws/aws-tg-4.png)

### 5. Save Target
After we add instance with specific port to registered, then click "Save" button

![SSH Keys](/coding-guidelines/aws/aws-tg-5.png)

<center>- - - Finish - - -</center>
