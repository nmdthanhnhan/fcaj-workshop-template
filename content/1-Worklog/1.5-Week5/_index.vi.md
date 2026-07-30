---
title: "Worklog Tuần 5"
date: 2026-07-06
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu tuần 5:
* Team thiết kế toàn bộ kiến trúc giải pháp, vẽ sơ đồ và viết Proposal dự án.
* Quản lý vòng đời mô hình với SageMaker Model Registry.
* Thiết lập cơ chế kiểm soát phiên bản (Model versioning).

### Các công việc triển khai trong tuần:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu chức năng của Amazon SageMaker Model Registry trong hệ sinh thái MLOps | 06/07/2026 | 06/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/model-registry.html> |
| 3 | - Nghiên cứu cơ chế Versioning và các trạng thái phê duyệt (Approval status) | 07/07/2026 | 07/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/model-registry-version.html> |
| 4 | - **Team:** Thiết kế toàn bộ kiến trúc MLOPS Pipeline - S3 => Pipeline 4 bước => Model Registry => EventBridge => Lambda Deployer => Serverless Endpoint<br>- **Team:** Viết Proposal - Problem Statement, Solution Architecture, Timeline | 08/07/2026 | 08/07/2026 | AWS Architecture Center |
| 5 | - Khởi tạo Model Group và đăng ký (Register) mô hình tốt nhất vào Model Registry | 09/07/2026 | 09/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/model-registry-register.html> |
| 6 | - Cập nhật trạng thái phê duyệt của mô hình (từ PendingManualApproval sang Approved) | 10/07/2026 | 10/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/model-registry-approve.html> |

### Kết quả đạt được:
* Hoàn thiện bản thiết kế kiến trúc toàn diện và Proposal cho dự án cùng với team.
* Hệ thống hóa thành công các phiên bản mô hình sau khi huấn luyện vào SageMaker Model Registry.
* Đưa mô hình vào trạng thái chuẩn hóa, sẵn sàng cho giai đoạn tự động hóa và triển khai.