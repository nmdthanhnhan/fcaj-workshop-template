---
title: "Worklog Tuần 3"
date: 2026-06-26
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Mục tiêu tuần 3:
* Tìm hiểu các phương pháp huấn luyện mô hình (Training) trên SageMaker.
* Phân tích và so sánh sự khác nhau giữa việc sử dụng Built-in algorithms và Custom scripts.

### Các công việc triển khai trong tuần:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Nghiên cứu cơ chế khởi tạo và quản lý máy chủ huấn luyện (Training Instances) của SageMaker | 22/06/2026 | 22/06/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/how-it-works-training.html> |
| 3 | - Tìm hiểu lý thuyết về các thuật toán tích hợp sẵn (Built-in algorithms) trên AWS, trọng tâm là XGBoost | 23/06/2026 | 23/06/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/xgboost.html> |
| 4 | - Phân tích cấu trúc và quy định chuẩn của một đoạn mã huấn luyện tùy chỉnh (Custom training script) | 24/06/2026 | 24/06/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/your-algorithms-training-algo.html> |
| 5 | - Nghiên cứu luồng di chuyển của dữ liệu khi khởi chạy SageMaker Training Job (từ S3 vào Container và xuất artifacts về lại S3) | 25/06/2026 | 25/06/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/model-train.html> |
| 6 | - Tìm hiểu cơ chế giám sát quá trình huấn luyện và cách phân tích log thông qua Amazon CloudWatch | 26/06/2026 | 26/06/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/logging-cloudwatch.html> |

### Kết quả đạt được:
* Nắm quy trình đóng gói, cấp phát tài nguyên và vận hành mã huấn luyện trên môi trường Cloud.
* Sẵn sàng khối lượng kiến thức lý thuyết cần thiết để có thể tiến hành thực hành xây dựng Pipeline ở các tuần tiếp theo.