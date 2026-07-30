---
title: "Worklog Week 6"
date: 2026-07-06
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Objectives for Week 6:
* Deploy the model to SageMaker Endpoint for real-time inference.
* Integrate Amazon API Gateway and AWS Lambda to create a REST API.

### Tasks to be implemented this week:
| Day | Task | Start Date | End Date | References |
| --- | --- | --- | --- | --- |
| Mon | - Learn the real-time inference deployment architecture of SageMaker | 06/07/2026 | 06/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/realtime-endpoints.html> |
| Tue | - Deploy the Approved model version from Registry to SageMaker Endpoint | 07/07/2026 | 07/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/model-registry-deploy.html> |
| Wed | - Learn the Serverless integration architecture with API Gateway and Lambda | 08/07/2026 | 08/07/2026 | <https://docs.aws.amazon.com/apigateway/latest/developerguide/welcome.html> |
| Thu | - Write an AWS Lambda function (using Python Boto3) to call `InvokeEndpoint` to SageMaker | 09/07/2026 | 09/07/2026 | <https://docs.aws.amazon.com/lambda/latest/dg/welcome.html> |
| Fri | - Configure Amazon API Gateway to expose REST API externally <br> - Send API test requests using Postman/cURL | 10/07/2026 | 10/07/2026 | <https://docs.aws.amazon.com/apigateway/latest/developerguide/getting-started-with-lambda-integration.html> |

### Achievements for Week 6:
* The Machine Learning model is ready to serve real-world traffic.
* Completed the communication flow from Client -> API Gateway -> Lambda -> SageMaker Endpoint.