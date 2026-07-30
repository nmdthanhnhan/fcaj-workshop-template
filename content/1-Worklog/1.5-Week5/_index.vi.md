---
title: "Worklog Tuần 5"
date: 2026-06-29
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu tuần 5:
* Quản lý vòng đời mô hình với SageMaker Model Registry.
* Thiết lập kiểm soát phiên bản (Model versioning).

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu chức năng của Amazon SageMaker Model Registry trong hệ sinh thái MLOps | 29/06/2026 | 29/06/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/model-registry.html> |
| 3 | - Nghiên cứu cơ chế Versioning và các trạng thái phê duyệt (Approval status) của mô hình | 30/06/2026 | 30/06/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/model-registry-version.html> |
| 4 | - Khởi tạo Model Group để tổ chức các phiên bản mô hình | 01/07/2026 | 01/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/model-registry-model-group.html> |
| 5 | - Đóng gói và đăng ký (Register) mô hình tối ưu nhất vào Model Registry | 02/07/2026 | 02/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/model-registry-register.html> |
| 6 | - Đánh giá và cập nhật trạng thái phê duyệt (từ PendingManualApproval sang Approved) | 03/07/2026 | 03/07/2026 | <https://docs.aws.amazon.com/sagemaker/latest/dg/model-registry-approve.html> |

### Kết quả đạt được tuần 5:
* Hệ thống hóa được các phiên bản mô hình sau khi huấn luyện.
* Chuẩn bị sẵn sàng mô hình đạt tiêu chuẩn để đưa vào giai đoạn triển khai (Deployment).