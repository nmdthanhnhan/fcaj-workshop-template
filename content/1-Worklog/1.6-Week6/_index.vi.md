---
title: "Worklog Tuần 6"
date: 2026-07-13
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Mục tiêu tuần 6:
* Xây dựng hoàn chỉnh SageMaker Pipeline (Bao gồm Processing, HPO, Evaluation, ConditionStep AUC >= 0.80, Register).
* Đảm bảo tự động hóa toàn bộ luồng huấn luyện Machine Learning.

### Các công việc triển khai trong tuần:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu kiến trúc Pipeline Definition của SageMaker bằng Python SDK | 13/07/2026 | 13/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/build-and-manage-pipeline.html> |
| 3 | - Thiết lập Processing Step và Tuning Step trong chuỗi tự động hóa | 14/07/2026 | 14/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/build-and-manage-steps.html> |
| 4 | - Thiết lập Evaluation Step để đo lường độ chính xác sau khi Training | 15/07/2026 | 15/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/build-and-manage-steps.html> |
| 5 | - Thiết lập Condition Step và Model Step để kiểm duyệt mô hình trước khi lưu trữ | 16/07/2026 | 16/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/build-and-manage-steps.html> |
| 6 | - **Team:** Xây dựng SageMaker Pipeline - ProcessingStep => TuningStep => EvalStep => ConditionStep (AUC >= 0.80) => ModelStep (Register)<br>- **Team:** Test thực thi Pipeline toàn diện | 17/07/2026 | 17/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/pipelines.html> |

### Kết quả đạt được:
* Đạt được mức độ tự động hóa cao (chuẩn MLOps) cho quá trình huấn luyện và đánh giá mô hình.
* Xây dựng thành công SageMaker Pipeline hoàn chỉnh, xâu chuỗi mượt mà từ bước xử lý dữ liệu (Processing) đến khi đăng ký mô hình (Register).
* Giảm thiểu hoàn toàn các thao tác thủ công trong vòng đời phát triển Machine Learning.