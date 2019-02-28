---
title: "Create Security Group"
date: 2018-11-21T14:00:00+07:00
draft: false
weight: 3
---

### 1. Choose EC2
After Sign In success, click menu "Service" on header, then click "EC2".

![SSH Keys](/coding-guidelines/aws/aws-service.png)

### 2. Create Security Group
Click "Security Groups" on left menu, then click "Create Security Group" button to create a new security group.

![SSH Keys](/coding-guidelines/aws/aws-sg-1.png)

#### 2.1 Create Security Group of Load Balancer
We create a new security group for load balancer. For this security group, we only make it once that is used by all instance security groups.

Next, "Add Rule" to add HTTP and HTTPS ports. If finish, then click "Create" button.

![SSH Keys](/coding-guidelines/aws/aws-sg-2.png)

#### 2.2 Create Security Group of Instance
We create a new security group, the name depends the project name. If the project name is **"Project Sample Staging"**, so the security group name is **"project-sample-staging-sg"**, add **"sg"** after project name.

Next, "Add Rule" to add the all ports that we use. On "Source" input, we choose Load Balancer Security Group. If finish, then click "Create" button.

![SSH Keys](/coding-guidelines/aws/aws-sg-3.png)

<center>- - - Finish - - -</center>
