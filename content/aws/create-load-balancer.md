---
title: "Create Load Balancer"
date: 2018-11-21T14:00:00+07:00
draft: false
weight: 5
---

### 1. Choose EC2
After Sign In success, click menu "Service" on header, then click "EC2".

![SSH Keys](/coding-guidelines/aws/aws-service.png)

### 2. Create Load Balancer
Click "Load Balancers" on left menu, then click "Create Load Balancer" button to create a new load balancer.

![SSH Keys](/coding-guidelines/aws/aws-lb-1.png)

### 3. Select Load Balancer type
Click "Create" button on "Application Load Balancer" with HTTP/HTTPS logo.

![SSH Keys](/coding-guidelines/aws/aws-lb-2.png)

### 4. Configure Load Balancer
Type the Load Balancer name, then Add "HTTPS" on Listeners, then choose 2 Availability Zones, then click "Next: Configure Security Settings".

![SSH Keys](/coding-guidelines/aws/aws-lb-3.png)

### 5. Configure Security Settings
Choose our ACM, then click "Next: Configure Security Groups".

p.s: If there is no ACM yet, you can click this link

![SSH Keys](/coding-guidelines/aws/aws-lb-4.png)

### 6. Configure Security Groups
Choose Security Groups for Load Balancer, then click "Next: Configure Routing".

p.s: If there is no Security Groups for Load Balancer yet, you can click this link

![SSH Keys](/coding-guidelines/aws/aws-lb-5.png)

### 7. Configure Routing
Choose our target group, then click "Next: Register Targets".

p.s: If there is no target group yet, you can click this link

![SSH Keys](/coding-guidelines/aws/aws-lb-6.png)

### 8. Register Targets
Review our register targets, then click "Next: Review".

![SSH Keys](/coding-guidelines/aws/aws-lb-7.png)

### 9. Review
Review our load balancer, then click "Create".

![SSH Keys](/coding-guidelines/aws/aws-lb-8.png)

<center>- - - Finish - - -</center>
