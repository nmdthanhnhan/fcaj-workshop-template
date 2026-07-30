---
title: "Blog 3"
date: 2026-07-30
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---

# COMMON ERRORS WHEN DEPLOYING APPLICATIONS AND HOW AWS HELPS RESOLVE THEM

[Link blog 3](https://www.facebook.com/share/p/18aas3Dc43/)

After learning about deploying applications on AWS, our team realized that writing an application is just the first step. In reality, the operational phase is where most problems arise. An application might run perfectly on a personal machine, but when deployed to the Cloud, it can encounter numerous errors that prevent users from accessing it. Below are some common situations we learned about while studying AWS.

Key takeaways:

* Cannot Access the Website: This is the most common error, often resulting in a "This site can't be reached" or timeout message. Causes range from unstarted EC2 instances and incorrect IPs to Security Groups missing inbound rules (e.g., opening only SSH port 22 but forgetting HTTP 80 or HTTPS 443).
* HTTP 403 Forbidden: This means the request reached the server but lacks permission. In AWS, this typically occurs due to missing IAM User permissions, unassigned IAM Roles, or misconfigured Amazon S3 Bucket Policies. AWS encourages using IAM Roles for temporary permissions instead of hardcoding Access Keys.
* HTTP 500 Internal Server Error: A generic browser error that hides actual root causes like code exceptions, database timeouts, missing environment variables, or memory exhaustion. Amazon CloudWatch is crucial here to collect Application and System Logs, enabling faster troubleshooting.
* Server Overload During Traffic Spikes: A system running smoothly for a few users can crash when hundreds access it simultaneously, causing high CPU utilization and request timeouts. Combining Amazon EC2 Auto Scaling with an Elastic Load Balancer automatically provisions more servers to distribute the load and maintain performance.
* Data Loss After Server Replacement: Storing uploaded files directly on an EC2 instance risks permanent data loss if the server crashes. Amazon S3 should be used to store images, videos, and backups, decoupling data storage from application logic to reduce risk and improve scalability.

Most application deployment issues do not stem from "bad code", but rather from how the system is configured and operated. A stable application requires comprehensive logging, proper access management, fault-tolerant design, and a solid scalability plan. This is why AWS builds a complete ecosystem supporting the deployment, monitoring, and operation of applications in real-world environments.


References:

* [Auto Scaling Documentation](https://docs.aws.amazon.com/autoscaling/)
* [Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html)
* [CloudWatch](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/WhatIsCloudWatch.html)
* [AWS Identity and Access Management](https://docs.aws.amazon.com/iam/)
