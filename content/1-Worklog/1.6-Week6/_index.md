---
title: "Worklog Week 6"
date: 2026-07-13
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Objectives for Week 6:
* Build the complete SageMaker Pipeline (Processing, HPO, Evaluation, ConditionStep AUC >= 0.80, Register).
* Automate the entire Machine Learning training workflow.

### Tasks to be implemented this week:
| Day | Task | Start Date | End Date | References |
| --- | --- | --- | --- | --- |
| Mon | - Learn the Pipeline Definition architecture of SageMaker using Python SDK | 13/07/2026 | 13/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/build-and-manage-pipeline.html> |
| Tue | - Configure Processing Step and Tuning Step in the automation chain | 14/07/2026 | 14/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/build-and-manage-steps.html> |
| Wed | - Configure Evaluation Step to measure accuracy after Training | 15/07/2026 | 15/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/build-and-manage-steps.html> |
| Thu | - Configure Condition Step and Model Step to validate the model before registering | 16/07/2026 | 16/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/build-and-manage-steps.html> |
| Fri | - **Team:** Build SageMaker Pipeline - ProcessingStep => TuningStep => EvalStep => ConditionStep (AUC >= 0.80) => ModelStep (Register)<br>- **Team:** Test Pipeline execution | 17/07/2026 | 17/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/pipelines.html> |

### Achievements for Week 6:
* Achieved a high level of automation (MLOps standard) for the model training and evaluation process.
* Successfully built a complete SageMaker Pipeline, smoothly chaining from data processing to model registration.
* Completely minimized manual operations in the Machine Learning development lifecycle.