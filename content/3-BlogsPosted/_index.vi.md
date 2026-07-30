---
title: "Các bài Blog đã đăng"
date: 2026-07-30
weight: 3
chapter: false
pre: " <b> 3. </b> "
---


Phần này sẽ liệt kê và giới thiệu các bài blogs mà bạn đã đăng lên [AWS Study Group](https://www.facebook.com/groups/awsstudygroupfcj).

### [Blog 1 - BÀI TOÁN CẠN KIỆT KẾT NỐI GIỮA AWS LAMBDA VÀ AMAZON RDS](3.1-Blog1/)
Bài viết này chia sẻ chi tiết về bài toán Cạn kiệt kết nối (Connection Exhaustion) khi kết hợp kiến trúc phi máy chủ AWS Lambda với cơ sở dữ liệu quan hệ (Amazon RDS). Đồng thời, bài viết cũng phân tích cách Amazon RDS Proxy hoạt động như một lớp màng lọc trung gian (Multiplexing) để giải quyết triệt để nút thắt cổ chai này, giúp hệ thống mở rộng linh hoạt mà vẫn đảm bảo an toàn.

### [Blog 2 - BẢO MẬT TRONG PHÁT TRIỂN PHẦN MỀM – KHÔNG CHỈ LÀ VIẾT CODE AN TOÀN](3.2-Blog2/)
Một ứng dụng chạy mượt mà chưa chắc đã là một ứng dụng an toàn khi đưa lên Internet. Bài blog này đúc kết những nguyên tắc bảo mật cốt lõi trên AWS như: không lưu Access Key trong mã nguồn, áp dụng quyền tối thiểu (Least Privilege), phân tách mạng Public/Private Subnet, và tận dụng các dịch vụ như AWS WAF, Amazon GuardDuty, Inspector để giám sát, bảo vệ hệ thống liên tục.

### [Blog 3 - NHỮNG LỖI THƯỜNG GẶP KHI TRIỂN KHAI ỨNG DỤNG VÀ CÁCH AWS GIÚP XỬ LÝ](3.3-Blog3/)
Quá trình vận hành thực tế trên Cloud luôn phát sinh nhiều vấn đề hơn lúc code trên máy cá nhân. Bài viết tổng hợp các lỗi kinh điển như không thể truy cập website, lỗi phân quyền 403 Forbidden, lỗi 500 Internal Server Error ẩn giấu nguyên nhân thực sự, hay rủi ro mất dữ liệu, từ đó đưa ra các hướng giải quyết hiệu quả bằng hệ sinh thái quản lý của AWS.
