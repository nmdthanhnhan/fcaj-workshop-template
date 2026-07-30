---
title: "Worklog Tuần 4"
date: 2026-06-29
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục tiêu tuần 4:
* Team tìm hiểu khái niệm MLOps, các thành phần SageMaker và phân tích Telco Churn dataset.
* Theo dõi các thử nghiệm với SageMaker Experiments.
* Tối ưu hóa hiệu suất mô hình với Automatic Model Tuning (HPO).

### Các công việc triển khai trong tuần:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu công cụ Amazon SageMaker Experiments để theo dõi quy trình ML | 29/06/2026 | 29/06/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/experiments.html> |
| 3 | - Khởi tạo Experiment và ghi nhận các chỉ số (metrics) của mô hình | 30/06/2026 | 30/06/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/experiments-create.html> |
| 4 | - **Team:** Tổng quan MLOps - workflow End-to-End, các thành phần SageMaker (Studio, Processing Jobs, Training Jobs, Pipelines)<br>- **Team:** Phân tích dataset Telco Churn - cấu trúc đặc trưng, thống kê phân phối, xác định bài toán phân lớp nhị phân | 01/07/2026 | 01/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/whatis.html> |
| 5 | - Thiết lập không gian tìm kiếm (Search Space) và cấu hình Automatic Model Tuning job | 02/07/2026 | 02/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/automatic-model-tuning-define-metrics-variables.html> |
| 6 | - Phân tích kết quả tuning, trích xuất bộ siêu tham số mang lại độ chính xác cao nhất | 03/07/2026 | 03/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/automatic-model-tuning-monitor.html> |

### Kết quả đạt được:
* Phân tích thành công bài toán và dataset cùng với Team.
* Quản lý khoa học nhiều lần chạy (runs) của mô hình.
* Tự động hóa quá trình dò tìm cấu hình tối ưu thay vì thử nghiệm thủ công.