---
title: "Workshop"
date: 2026-07-29
weight: 5
chapter: false
pre: " <b> 5. </b> "
---


# Automating MLOps Workflow and Deploying Telco Customer Churn Prediction Model on AWS

#### Overview

In a real-world enterprise environment, Machine Learning models often encounter Data Drift (degradation of prediction quality over time) and require significant effort to operate and update manually.

This Workshop will guide you step-by-step to build a closed End-to-End Automated MLOps Platform on the AWS Cloud for the Telco Customer Churn Prediction problem.

The system combines the power of Event-Driven Automation architecture and AWS Serverless Services:

*   **Automated Retrain Trigger:** Checks for Data Drift and triggers the SageMaker Pipeline as soon as an Admin uploads new data to Amazon S3.
*   **Standard 4-step MLOps Workflow (SageMaker Pipeline):** Automates the process from Data Preprocessing (SKLearnProcessor), Training & Hyperparameter Tuning (HyperparameterTuner), Model Quality Evaluation (ScriptProcessor), to checking the Quality Gate ($AUC \ge 0.80$).
*   **Continuous Deployment (CD):** Uses Amazon EventBridge to listen for the "Approved" label event in the Model Registry, triggering AWS Lambda to automatically create configurations and update the SageMaker Serverless Endpoint without causing service interruption (Zero-Downtime Deployment).
*   **Real-time Inference API:** Integrates Amazon API Gateway (HTTP API) and Lambda Inference Handler to receive HTTPS requests and instantly return the Churn probability.
*   **Monitoring & Alerts:** Centralizes log management via CloudWatch Logs, sets up CloudWatch Alarms, and sends automated Email notifications via Amazon SNS.

#### Content

1. [Overview (Workshop Overview)](5.1-Workshop-overview/)
2. [Prerequisites](5.2-Prerequiste/)
3. [Step-by-Step Implementation](5.3-Implementation/)
4. [Test & Validation](5.4-Test-Validation/)
5. [Resource Clean-up](5.5-Cleanup/)
