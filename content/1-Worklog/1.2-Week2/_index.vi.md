---
title: "Worklog Tuần 2"
date: 2026-06-08
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Mục tiêu tuần 2:
* Chuẩn bị và xử lý dữ liệu (Data preprocessing & feature engineering).
* Sử dụng SageMaker Processing Jobs để tự động hóa quy trình xử lý dữ liệu.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu các kỹ thuật xử lý dữ liệu và trích xuất đặc trưng (Feature engineering) | 08/06/2026 | 08/06/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/how-it-works-training.html> |
| 3 | - Nghiên cứu cơ chế hoạt động của Amazon SageMaker Processing Jobs | 09/06/2026 | 09/06/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/processing-job.html> |
| 4 | - Viết mã nguồn Python (sử dụng Scikit-learn/Pandas) để tiền xử lý tập dữ liệu thô | 10/06/2026 | 10/06/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/use-scikit-learn-processing-container.html> |
| 5 | - Cấu hình và khởi chạy SageMaker Processing Job | 11/06/2026 | 11/06/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/processing-job-create.html> |
| 6 | - Kiểm tra dữ liệu đầu ra trên Amazon S3 và đánh giá chất lượng tập dữ liệu đã xử lý | 12/06/2026 | 12/06/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/processing-job-troubleshooting.html> |

### Kết quả đạt được tuần 2:
* Hiểu và viết được mã nguồn xử lý dữ liệu quy mô lớn.
* Chuyển đổi thành công dữ liệu thô thành tập dữ liệu huấn luyện (Training data) và kiểm thử (Test data) bằng SageMaker Processing Jobs.