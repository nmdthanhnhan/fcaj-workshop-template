---
title: "Overview"
date: 2026-07-29
weight: 1
chapter: false
pre: " <b> 5.1. </b> "
---


# Workshop Overview: MLOps Platform for Telco Customer Churn Prediction

#### Introduction to the Problem
In the telecommunications (Telco) industry, the cost of acquiring a new customer is often 5 to 25 times higher than the cost of retaining an existing one. Early prediction of customer churn risk allows the customer care department to proactively offer timely promotional and support policies.

However, real-world Machine Learning models often encounter Data Drift or Model Drift—where prediction quality degrades over time due to changing user habits. Furthermore, manually training and deploying models from Jupyter Notebooks to Production environments is time-consuming and prone to operational errors.

This workshop will guide you in building a closed End-to-End Automated MLOps Platform on the AWS Cloud to thoroughly resolve the challenges mentioned above.

#### Workshop Objectives
After completing this lab, you will master and be able to deploy:

*   **Real-time Inference:** Integrate Amazon API Gateway, AWS Lambda, and AWS SageMaker Serverless Endpoint to process requests and instantly return churn probabilities with optimal costs ($0 when there is no traffic).
*   **Event-Driven Trigger:** Automatically detect when an Admin uploads new data to Amazon S3, check for Data Drift, and trigger the Retrain workflow.
*   **MLOps Workflow (SageMaker Pipeline - 4 steps):**
    *   `TelcoChurnProcessStep`: Data preprocessing and Train/Validation/Test splitting (SKLearnProcessor).
    *   `TelcoChurnHpoStep`: Automated training & hyperparameter tuning with the XGBoost model (HyperparameterTuner).
    *   `TelcoChurnEvalStep`: Model quality evaluation on the Test set (ScriptProcessor).
    *   `ConditionStep`: Quality threshold check ($AUC \ge 0.80$). If met, the model is automatically registered into the SageMaker Model Registry in the Approved state.
*   **Continuous Deployment (CD):** Use Amazon EventBridge to listen for the Approved state from the Model Registry, triggering the AWS Lambda Deployer to automatically update the Serverless Endpoint without service interruption (Zero-Downtime Deployment).
*   **Monitoring & Alerting:** Centralize log storage via CloudWatch Logs, set up CloudWatch Alarms, and send automated warning emails to your inbox via Amazon SNS.

#### System Architecture Diagram

![System Architecture Diagram](/images/5-Workshop/5.1-Workshop-overview/diagram.png)

**AWS Services Used:**
*   **Amazon S3:** Stores Raw Data, Processed Data, and Model Artifacts.
*   **Amazon API Gateway & AWS Lambda:** Provides the REST API endpoint and handles real-time request data preprocessing.
*   **AWS SageMaker Serverless Endpoint:** Deploys the XGBoost model in a Serverless format with auto-scaling capabilities.
*   **AWS SageMaker Pipelines:** Manages and orchestrates the automated 4-step ML workflow.
*   **AWS SageMaker Model Registry:** Stores and manages model versions centrally.
*   **Amazon EventBridge:** Listens for state transition events from the Pipeline and Model Registry.
*   **Amazon SNS:** Sends automated Email notifications regarding Retrain results and incident alerts.
*   **Amazon CloudWatch:** Stores system logs, monitors metrics, and issues error alerts.

#### Estimated Time & Cost
*   **Estimated time:** ~60 - 90 minutes.
*   **Infrastructure cost:** ~$0.50 - $1.00 USD (If resources are cleaned up properly according to the Clean-up step at the end of the lab, most services will fall within the AWS Free Tier).
