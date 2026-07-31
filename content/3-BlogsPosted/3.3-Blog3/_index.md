---
title: "Infrastructure Management with Terraform – Not Just Clicking on the Console"
date: 2026-07-31
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---

# INFRASTRUCTURE MANAGEMENT WITH TERRAFORM – NOT JUST CLICKING ON THE CONSOLE

[Link to the post](https://www.facebook.com/share/p/1JCgUcBu4c/)

During the process of learning and working on Cloud projects, creating resources by clicking on the AWS Management Console is very intuitive but reveals many risks when the project scales (hard to replicate systems, risk of misclicks, hard to recover). This article will share in detail the journey of abandoning the "ClickOps" habit to embrace the Infrastructure as Code (IaC) mindset through Terraform — a solution to manage the entire cloud infrastructure using source code instead of manual operations.

Key takeaways to grasp:

* Turning infrastructure into source code (IaC): Define all resources (Server, Network, Database, Firewall) as configuration files using HCL (HashiCorp Configuration Language), allowing for Git storage, code review, and easy version history management.
* Avoiding risks on Production with "Plan" and "Apply": The **terraform plan** mechanism allows you to preview exact changes (Create, Modify, Delete) before actual execution, drastically minimizing the risk of misconfiguration or accidental deletion of critical infrastructure.
* Centralized and secure State Management: Solves data conflict and security leakage issues during teamwork by using a Remote Backend (storing the **terraform.tfstate** file on Amazon S3) combined with the State Locking mechanism (via DynamoDB).
* Code reusability with Modules: Packages related resource clusters into standard Modules (like VPC, RDS) for flexible reuse, ensuring the Dev and Prod environments are 100% architecturally identical.
* Infrastructure Drift Control: Automatically scans and detects deviations when someone manually modifies the infrastructure on the Console, thereby proposing a plan to synchronize the system back to the correct standard state (Single Source of Truth) defined in the code.

Shifting from a manual operation mindset to "Infrastructure as Code" requires a bit of initial familiarization time, but it is an indispensable skill for building standardized, reliable, and professional cloud systems.

![Infrastructure management model with Terraform](/images/blog3.jpg)

References:

* [Terraform AWS Provider Docs](https://registry.terraform.io/providers/hashicorp/aws/latest/docs)
* [Terraform Recommended Best Practices](https://developer.hashicorp.com/terraform/tutorials)
* [AWS Backend S3 & DynamoDB](https://developer.hashicorp.com/terraform/language/settings/backends/s3)
