---
title: "Blog 3"
date: 2026-07-31
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---

# QUẢN LÝ HẠ TẦNG VỚI TERRAFORM – KHÔNG CHỈ LÀ CLICK ON THE CONSOLE


[Link blog](https://www.facebook.com/share/p/1JCgUcBu4c/)


Trong quá trình học và làm dự án trên Cloud, việc tạo tài nguyên bằng thao tác click chuột trên AWS Management Console rất trực quan nhưng lại bộc lộ nhiều rủi ro khi dự án mở rộng (khó nhân bản hệ thống, rủi ro thao tác nhầm, khó khôi phục). Bài viết này sẽ chia sẻ chi tiết về hành trình từ bỏ thói quen "ClickOps" để đến với tư duy Infrastructure as Code (IaC) thông qua Terraform — giải pháp quản lý toàn bộ hạ tầng đám mây bằng mã nguồn thay vì thao tác thủ công.

Các điểm chính cần nắm:

* Biến hạ tầng thành mã nguồn (IaC): Định nghĩa toàn bộ tài nguyên (Server, Network, Database, Firewall) dưới dạng các file cấu hình bằng ngôn ngữ HCL, cho phép lưu trữ trên Git, review code và quản lý lịch sử thay đổi dễ dàng.
* Tránh rủi ro trên Production với "Plan" và "Apply": Cơ chế **terraform plan** cho phép xem trước chính xác những thay đổi (Tạo mới, Sửa đổi, Xóa bỏ) trước khi thực thi thực tế, giảm thiểu tối đa rủi ro cấu hình sai hoặc xóa nhầm hạ tầng quan trọng.
* Quản lý State tập trung và an toàn: Giải quyết bài toán xung đột dữ liệu và rò rỉ bảo mật khi làm việc nhóm bằng cách sử dụng Remote Backend (lưu file **terraform.tfstate** trên Amazon S3) kết hợp với cơ chế khóa State Locking (qua DynamoDB).
* Tái sử dụng code với Modules: Đóng gói các cụm tài nguyên liên quan thành các Module chuẩn (như VPC, RDS) để tái sử dụng linh hoạt, đảm bảo môi trường Dev và Prod đồng nhất 100% về mặt kiến trúc.
* Kiểm soát Infrastructure Drift: Tự động quét và phát hiện sự sai lệch khi có người tự ý sửa hạ tầng trên Console, từ đó đề xuất phương án đồng bộ hóa hệ thống về đúng trạng thái chuẩn (Single Source of Truth) đã định nghĩa trong code.

Chuyển từ tư duy thao tác tay sang "Infrastructure as Code" đòi hỏi một chút thời gian làm quen ban đầu, nhưng đây là kỹ năng không thể thiếu để xây dựng các hệ thống đám mây chuẩn hóa, tin cậy và chuyên nghiệp.

![Mô hình quản lý hạ tầng với Terraform](/images/blog3.jpg)

Tài liệu tham khảo:

* [Terraform AWS Provider Docs](https://registry.terraform.io/providers/hashicorp/aws/latest/docs)
* [Terraform Recommended Best Practices](https://developer.hashicorp.com/terraform/tutorials)
* [AWS Backend S3 & DynamoDB](https://developer.hashicorp.com/terraform/language/settings/backends/s3)
