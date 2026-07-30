---
title: "Worklog Tuần 3"
date: 2026-06-15
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Mục tiêu tuần 3:
* Huấn luyện mô hình Machine Learning (Training Jobs) trên SageMaker.
* Thử nghiệm các thuật toán có sẵn hoặc mã nguồn tùy chỉnh.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu cơ chế quản lý máy chủ huấn luyện (Training Instances) của SageMaker | 15/06/2026 | 15/06/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/how-it-works-training.html> |
| 3 | - Nghiên cứu các thuật toán tích hợp sẵn (Built-in algorithms) như XGBoost | 16/06/2026 | 16/06/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/xgboost.html> |
| 4 | - Viết mã nguồn huấn luyện (Training script) tùy chỉnh bằng Python | 17/06/2026 | 17/06/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/your-algorithms-training-algo.html> |
| 5 | - Khởi tạo và chạy SageMaker Training Job sử dụng dữ liệu từ S3 | 18/06/2026 | 18/06/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/model-train.html> |
| 6 | - Đánh giá quá trình huấn luyện và theo dõi logs thông qua Amazon CloudWatch | 19/06/2026 | 19/06/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/logging-cloudwatch.html> |

### Kết quả đạt được tuần 3:
* Nắm vững cách thức đóng gói và triển khai mã nguồn huấn luyện trên môi trường Cloud.
* Mô hình được huấn luyện thành công và mô hình (model artifacts) được lưu trữ an toàn về S3.