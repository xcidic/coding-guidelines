---
title: "Create Instance"
date: 2018-11-21T14:00:01+07:00
draft: false
weight: 2
---

### 1. Choose EC2
After Sign In success, click menu "Service" on header, then click "EC2".

![SSH Keys](/coding-guidelines/aws/aws-service.png)

### 2. Create Instance
After click EC2, click "Instances" on left menu, then click "Launch Instance" button to create a new instance.

![SSH Keys](/coding-guidelines/aws/aws-instance.png)

### 3. Choose Operation System
Choose the Operation System (OS), for Xcidic we choose "Ubuntu Server 16.04 LTS (HVM), SSD Volume Type".

![SSH Keys](/coding-guidelines/aws/aws-launch-instance-1.png)

### 4. Choose Instance Type
Choose the Instance Type. It depends the scope of project, for default we choose "t2.micro", then click "Next: Configure Instance Details" button.

![SSH Keys](/coding-guidelines/aws/aws-launch-instance-2.png)

### 5. Configure Instance Details
For this step we use AWS default, then click "Next: Add Storage" button.

![SSH Keys](/coding-guidelines/aws/aws-launch-instance-3.png)

### 6. Add Storage
For this step we use AWS default, then click "Next: Add Tags" button.

![SSH Keys](/coding-guidelines/aws/aws-launch-instance-4.png)

### 7. Add Tags
For default we don't add tags, then click "Next: Configure Security Group" button.

![SSH Keys](/coding-guidelines/aws/aws-launch-instance-5.png)

### 8. Configure Security Group
We create a new security group, the name depends the project name. If the project name is **"Project WW Staging"**, so the security group name is **"project-ww-staging-sg"**, add **"sg"** after project name.

Next, "Add Rule" to add the all ports that we use. On "Source" input, we choose Load Balancer Security Group. If finish, then click "Review and Launch" button.

\*p.s: If we haven't created Load Balancer Security Group yet, please click this [link]({{%relref "aws/create-instance.md" %}}).

![SSH Keys](/coding-guidelines/aws/aws-launch-instance-6.png)

### 9. Review the Instance
Review an instance detail. If we are sure to create this instance, just click "Launch" button. Finish. 😊

![SSH Keys](/coding-guidelines/aws/aws-launch-instance-7.png)

<center>- - - Finish - - -</center>
