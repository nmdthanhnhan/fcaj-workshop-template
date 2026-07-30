---
title: "Worklog Week 5"
date: 2026-07-06
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Objectives for Week 5:
* Design the full solution architecture, draw the architecture diagram, and write the Proposal.
* Manage model lifecycle with SageMaker Model Registry.
* Set up model versioning.

### Tasks to be implemented this week:
| Day | Task | Start Date | End Date | References |
| --- | --- | --- | --- | --- |
| Mon | - Learn the functions of Amazon SageMaker Model Registry in the MLOps ecosystem | 06/07/2026 | 06/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/model-registry.html> |
| Tue | - Research the Versioning mechanism and Approval status of models | 07/07/2026 | 07/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/model-registry-version.html> |
| Wed | - **Team:** Design full MLOPS Pipeline architecture - S3 => Pipeline 4 steps => Model Registry => EventBridge => Lambda Deployer => Serverless Endpoint<br>- **Team:** Write Proposal - Problem Statement, Solution Architecture, Timeline | 08/07/2026 | 08/07/2026 | AWS Architecture Center |
| Thu | - Initialize Model Group and register the best model to the Model Registry | 09/07/2026 | 09/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/model-registry-register.html> |
| Fri | - Evaluate and update the approval status (from PendingManualApproval to Approved) | 10/07/2026 | 10/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/model-registry-approve.html> |

### Achievements for Week 5:
* Completed the comprehensive architecture design and project Proposal with the Team.
* Successfully systematized model versions after training into SageMaker Model Registry.
* Brought the model to a standardized state, ready for the automation and deployment phase.