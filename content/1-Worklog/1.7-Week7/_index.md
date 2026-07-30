---
title: "Worklog Week 7"
date: 2026-07-13
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Objectives for Week 7:
* Set up a model monitoring system with SageMaker Model Monitor and CloudWatch.
* Detect Data Drift.

### Tasks to be implemented this week:
| Day | Task | Start Date | End Date | References |
| --- | --- | --- | --- | --- |
| Mon | - Learn the concepts of Data Drift, Model Quality Drift in ML operations | 13/07/2026 | 13/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor-data-quality.html> |
| Tue | - Enable Data Capture feature on SageMaker Endpoint to record data flows | 14/07/2026 | 14/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor-data-capture.html> |
| Wed | - Configure and run a Baseline Job to establish data quality standards | 15/07/2026 | 15/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor-create-baseline.html> |
| Thu | - Set up a Monitoring Schedule to periodically analyze real-time data against the Baseline | 16/07/2026 | 16/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor-scheduling.html> |
| Fri | - Integrate Amazon CloudWatch to set up Alarms when Data Drift is detected | 17/07/2026 | 17/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor-cloudwatch-metrics.html> |

### Achievements for Week 7:
* Mastered the operation and monitoring mechanism of model quality in a Production environment.
* The system can automatically alert when user-submitted data has a different distribution than the training data.