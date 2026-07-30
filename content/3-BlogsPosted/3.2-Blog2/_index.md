---
title: "Security in Software Development – More Than Just Writing Secure Code"
date: 2026-07-30
weight: 2
chapter: false
pre: " <b> 3.2. </b> "
---

# SECURITY IN SOFTWARE DEVELOPMENT – MORE THAN JUST WRITING SECURE CODE

[Link blogposted](https://www.facebook.com/share/p/18aas3Dc43/)

During our process of learning AWS, the team realized something quite interesting. When starting a new project, most of us only focus on "how to make the application work". But once the application is deployed to the Internet, a much more important question arises: how to keep the application secure? An application might run smoothly in terms of functionality, but with just a misconfiguration or a small vulnerability, data can be exposed or the system can be attacked at any time. AWS not only provides the infrastructure to deploy applications but also offers a suite of services to help build a secure architecture from the very beginning, rather than waiting for an incident to occur before patching it.

Key takeaways:

* Do not store Access Keys in the source code: Avoid exposing credentials on GitHub to prevent resource exploitation or massive unexpected costs; instead, use IAM Roles, Environment Variables, AWS Secrets Manager, or AWS Systems Manager Parameter Store.
* The "Least Privilege" principle: Grant only the exact permissions needed for a service (e.g., an EC2 instance only needs `s3:GetObject` for a specific bucket instead of FullAccess) to minimize damage in case of a breach.
* Not all resources should be exposed to the Internet: Avoid placing every service in a Public Subnet; instead, a secure architecture should route traffic through a Load Balancer, place the Backend in an appropriate Public/Private Subnet, and keep the Database in a Private Subnet.
* Protect the application from Web attacks: Use AWS WAF (Web Application Firewall) to filter malicious requests like SQL Injection, XSS, application-layer DDoS, or to rate-limit requests from suspicious IPs.
* Continuously monitor the system with specialized tools:
  * Amazon GuardDuty: Automatically detect anomalous behaviors based on CloudTrail, VPC Flow Logs, and DNS Logs.
  * Amazon Inspector: Scan for vulnerabilities within EC2 Instances, Container Images, and software libraries.
  * AWS Security Hub: Aggregate findings from various security services into a single dashboard.
* Solve practical scaling and storage problems: Combine Amazon EC2 Auto Scaling with an Elastic Load Balancer to prevent overload during traffic spikes, and simultaneously use Amazon S3 to decouple data storage from the application execution environment to avoid data loss when switching servers.

Integrating security and operational mindsets right from the start helps transform an architecture with hidden risks into a secure, flexible, and professional system when entering real-world projects.

![Security and operations architecture on AWS](/images/blog2.jpg)

References:

* [IAM best practices (AWS docs)](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html)
* [Well-Architected – IAM](https://docs.aws.amazon.com/wellarchitected/latest/framework/sec-iam.html)
* [AWS WAF](https://docs.aws.amazon.com/waf/latest/developerguide/what-is-aws-waf.html)
* [Amazon GuardDuty](https://docs.aws.amazon.com/guardduty/latest/ug/what-is-guardduty.html)
* [Amazon Inspector](https://aws.amazon.com/inspector/)
