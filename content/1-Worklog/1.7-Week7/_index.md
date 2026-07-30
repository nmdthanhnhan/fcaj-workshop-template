---
title: "Worklog Week 7"
date: 2026-07-20
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Objectives for Week 7:
* Implement EventBridge + Lambda Auto-Deploy, build the Inference API, and perform End-to-End testing.
* Ensure stable communication flow between Client and SageMaker Serverless Endpoint.

### Tasks to be implemented this week:
| Day | Task | Start Date | End Date | References |
| --- | --- | --- | --- | --- |
| Mon | - Learn the Amazon EventBridge trigger mechanism when Model Registry updates | 20/07/2026 | 20/07/2026 | <https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-what-is.html> |
| Tue | - Write AWS Lambda Auto-Deployer function to update the Endpoint | 21/07/2026 | 21/07/2026 | <https://docs.aws.amazon.com/lambda/latest/dg/welcome.html> |
| Wed | - Configure Amazon API Gateway to connect directly to the Inference function | 22/07/2026 | 22/07/2026 | <https://docs.aws.amazon.com/apigateway/latest/developerguide/getting-started-with-lambda-integration.html> |
| Thu | - Connect the entire system flow: Client -> API Gateway -> Lambda -> Endpoint | 23/07/2026 | 23/07/2026 | <https://docs.aws.amazon.com/apigateway/latest/developerguide/welcome.html> |
| Fri | - **Team:** End-to-End Testing - upload new data => DriftChecker trigger => Pipeline runs => Model Registered => Deployer updates Endpoint => Predict API returns results<br>- Analyze CloudWatch logs to verify each step | 24/07/2026 | 24/07/2026 | <https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/AnalyzingLogData.html> |

### Achievements for Week 7:
* Finalized the entire end-to-end Machine Learning solution, ready to serve real-world traffic.
* Successfully established a smooth API communication flow from Client -> API Gateway -> Lambda -> SageMaker Endpoint.
* Mastered system monitoring via CloudWatch and ensured the Auto-Deploy feature works accurately with new data/models.