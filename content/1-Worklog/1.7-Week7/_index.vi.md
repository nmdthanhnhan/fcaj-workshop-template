---
title: "Worklog Tuần 7"
date: 2026-07-13
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục tiêu tuần 7:
* Thiết lập hệ thống theo dõi mô hình (Monitoring) với SageMaker Model Monitor và CloudWatch.
* Phát hiện hiện tượng trôi dạt dữ liệu (Data Drift).

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu khái niệm Data Drift, Model Quality Drift trong vận hành ML | 13/07/2026 | 13/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor-data-quality.html> |
| 3 | - Bật tính năng Data Capture trên SageMaker Endpoint để ghi lại luồng dữ liệu | 14/07/2026 | 14/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor-data-capture.html> |
| 4 | - Cấu hình và chạy Baseline Job để định hình chuẩn chất lượng của dữ liệu | 15/07/2026 | 15/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor-create-baseline.html> |
| 5 | - Thiết lập Monitoring Schedule định kỳ phân tích dữ liệu thực tế so với Baseline | 16/07/2026 | 16/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor-scheduling.html> |
| 6 | - Tích hợp Amazon CloudWatch để thiết lập cảnh báo (Alarms) khi phát hiện Data Drift | 17/07/2026 | 17/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor-cloudwatch-metrics.html> |

### Kết quả đạt được tuần 7:
* Nắm vững cơ chế vận hành và giám sát chất lượng mô hình trong môi trường Production.
* Hệ thống có khả năng tự động cảnh báo khi dữ liệu người dùng gửi lên có phân phối khác biệt so với dữ liệu huấn luyện.