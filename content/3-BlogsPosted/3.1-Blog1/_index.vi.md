---
title: "Bài toán cạn kiệt kết nối giữa AWS Lambda và Amazon RDS"
date: 2026-07-29
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

# BÀI TOÁN CẠN KIỆT KẾT NỐI GIỮA AWS LAMBDA VÀ AMAZON RDS

[Link bài đăng](https://www.facebook.com/share/p/17yd4RF4ZF/)

Khi mang những lý thuyết chuẩn mực về Connection Pooling (Hồ chứa kết nối) lên áp dụng trên môi trường điện toán đám mây với kiến trúc phi máy chủ (Serverless), chúng ta lại đụng phải một "cơn ác mộng" thực sự về mặt kiến trúc hệ thống. Bài viết này sẽ chia sẻ chi tiết về bài toán Cạn kiệt kết nối (Connection Exhaustion) khi kết hợp AWS Lambda với cơ sở dữ liệu quan hệ (RDBMS), và cách Amazon RDS Proxy giải quyết triệt để nút thắt này.

Các điểm chính cần nắm:

* Sự xung đột kiến trúc: AWS Lambda linh hoạt, vô trạng thái và scale chớp nhoáng, trong khi Amazon RDS tiêu tốn tài nguyên cho mỗi kết nối (ví dụ ~10MB RAM/process cho PostgreSQL) và có giới hạn max_connections khắt khe.
* Khi có đợt truy cập lớn, hàng nghìn hàm Lambda tự động mở kết nối mới tới DB, khiến RDS quá tải và từ chối phục vụ (lỗi Too many connections), làm sập hệ thống dây chuyền.
* Connection Pooling truyền thống (bằng pg-pool, HikariCP) trở nên vô dụng do mỗi hàm Lambda chạy trên một môi trường cô lập, tạo ra hàng nghìn pool độc lập gây cạn kiệt tài nguyên gấp bội.
* Amazon RDS Proxy hoạt động như một lớp màng lọc trung gian, cung cấp tính năng Connection Pooling tập trung (Multiplexing) giúp hàng nghìn Lambda dùng chung chỉ vài chục kết nối DB thực tế đang rảnh.
* Hỗ trợ xử lý mượt mà khi chuyển đổi dự phòng (Failover): RDS Proxy chủ động giữ các truy vấn của Lambda lại trong hàng đợi thay vì báo lỗi rớt mạng khi máy chủ DB chính bị sập.
* Nâng cấp bảo mật với IAM Authentication: Cho phép hàm Lambda xác thực qua IAM Role thay vì dùng mật khẩu dạng văn bản rõ (plaintext) trong biến môi trường.

Việc tích hợp Amazon RDS Proxy biến một kiến trúc tiềm ẩn rủi ro "nghẽn cổ chai" thành một hệ thống linh hoạt, tự do mở rộng đón hàng chục nghìn lượt truy cập mà cơ sở dữ liệu phía sau vẫn bình yên vô sự.


![Kiến trúc hoạt động của Amazon RDS Proxy](/images/post1.png)

Tài liệu tham khảo:

* [Tổng quan về quản lý kết nối với Amazon RDS Proxy](https://aws.amazon.com/rds/proxy/)
* [Cách RDS Proxy hoạt động với AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/configuration-database.html)
* [Cơ chế Multiplexing và quản lý trạng thái kết nối](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/rds-proxy.html)



