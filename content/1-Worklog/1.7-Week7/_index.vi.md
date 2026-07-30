---
title: "Worklog Tuần 7"
date: 2026-07-20
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục tiêu tuần 7:
* Triển khai EventBridge + Lambda Auto-Deploy, xây dựng Inference API và thực hiện End-to-End testing.
* Đảm bảo luồng giao tiếp giữa Client và SageMaker Serverless Endpoint hoạt động ổn định.

### Các công việc triển khai trong tuần:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu cơ chế Trigger của Amazon EventBridge khi Model Registry cập nhật | 20/07/2026 | 20/07/2026 | <https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-what-is.html> |
| 3 | - Viết hàm AWS Lambda Auto-Deployer cập nhật Endpoint tự động | 21/07/2026 | 21/07/2026 | <https://docs.aws.amazon.com/lambda/latest/dg/welcome.html> |
| 4 | - Cấu hình Amazon API Gateway để kết nối trực tiếp với hàm Inference | 22/07/2026 | 22/07/2026 | <https://docs.aws.amazon.com/apigateway/latest/developerguide/getting-started-with-lambda-integration.html> |
| 5 | - Kết nối toàn bộ luồng hệ thống: Client -> API Gateway -> Lambda -> Endpoint | 23/07/2026 | 23/07/2026 | <https://docs.aws.amazon.com/apigateway/latest/developerguide/welcome.html> |
| 6 | - **Team:** Testing End-to-End - upload data mới => trigger DriftChecker => Pipeline chạy => Đăng ký Model => Deployer cập nhật Endpoint => Predict API trả kết quả<br>- Phân tích CloudWatch logs để xác minh từng bước | 24/07/2026 | 24/07/2026 | <https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/AnalyzingLogData.html> |

### Kết quả đạt được:
* Hoàn thiện toàn bộ giải pháp Machine Learning end-to-end, sẵn sàng phục vụ traffic thực tế.
* Thiết lập thành công luồng giao tiếp API mượt mà từ Client -> API Gateway -> Lambda -> SageMaker Endpoint.
* Nắm vững cơ chế theo dõi hệ thống qua CloudWatch và đảm bảo tính năng Auto-Deploy hoạt động chính xác khi có dữ liệu/mô hình mới.