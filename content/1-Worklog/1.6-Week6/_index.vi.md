---
title: "Worklog Tuần 6"
date: 2026-07-06
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Mục tiêu tuần 6:
* Triển khai mô hình lên SageMaker Endpoint để dự đoán theo thời gian thực (Real-time inference).
* Tích hợp Amazon API Gateway và AWS Lambda để tạo REST API.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu kiến trúc triển khai dự đoán theo thời gian thực của SageMaker | 06/07/2026 | 06/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/realtime-endpoints.html> |
| 3 | - Triển khai phiên bản mô hình đã Approved từ Registry lên SageMaker Endpoint | 07/07/2026 | 07/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/model-registry-deploy.html> |
| 4 | - Tìm hiểu kiến trúc tích hợp Serverless với API Gateway và Lambda | 08/07/2026 | 08/07/2026 | <https://docs.aws.amazon.com/apigateway/latest/developerguide/welcome.html> |
| 5 | - Viết hàm AWS Lambda (bằng Python Boto3) để gọi `InvokeEndpoint` tới SageMaker | 09/07/2026 | 09/07/2026 | <https://docs.aws.amazon.com/lambda/latest/dg/welcome.html> |
| 6 | - Cấu hình Amazon API Gateway để expose REST API ra bên ngoài <br> - Gửi request kiểm thử API bằng Postman/cURL | 10/07/2026 | 10/07/2026 | <https://docs.aws.amazon.com/apigateway/latest/developerguide/getting-started-with-lambda-integration.html> |

### Kết quả đạt được tuần 6:
* Mô hình Machine Learning đã sẵn sàng phục vụ lưu lượng thực tế.
* Hoàn thành luồng giao tiếp từ Client -> API Gateway -> Lambda -> SageMaker Endpoint.