---
title: "Event 1"
date: 2026-06-07
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

# Ghi Chép Cá Nhân: Buổi gặp gỡ FCAJ 06-06-2026

**Ngày tổ chức:** 6 tháng 6, 2026.  
**Hình thức:** Gặp mặt trực tiếp.  
**Địa điểm:** Tầng 26, Tòa nhà Bitexco, 02 Hải Triều, Phường Bến Nghé, TP. Hồ Chí Minh.  
**Ban tổ chức:** Cộng đồng First Cloud & AI Journey (FCAJ).

---

### Mục Đích Của Buổi Meetup

*   Theo mình cảm nhận, sự kiện này tạo ra một không gian rất cởi mở để anh em trong cộng đồng có thể thoải mái chia sẻ kiến thức kỹ thuật và những kinh nghiệm thực chiến với nhau.
*   Đây là dịp tuyệt vời để mọi người giới thiệu các dự án thực tế đang ứng dụng công nghệ Cloud và AI.
*   Buổi gặp gỡ cũng truyền cảm hứng rất lớn cho mình thông qua những câu chuyện thăng tiến nghề nghiệp trong ngành công nghệ.
*   Cuối cùng, sự kiện giúp mình kết nối được với rất nhiều thành viên đến từ đa dạng lĩnh vực và nền tảng khác nhau.

---

### Danh Sách Diễn Giả & Chủ Đề

| STT | Diễn giả | Chủ đề |
|-----|----------|--------|
| 1 | **Mr. Nguyễn Quốc Bảo** | Rock Paper Scissors với AWS WebSocket – Game Multiplayer Real-time |
| 2 | **Mr. Huỳnh Nguyễn Quốc Bảo** | Docker Basics – Ảo hóa & Container hóa |
| 3 | **Mr. Đinh Việt Phát** | GraphRAG – Truy xuất thông tin dựa trên đồ thị tri thức |
| 4 | **Mr. Lê Hoàng Gia Đại** | AWS WAF & NIDS dùng Machine Learning |
| 5 | **Mr. Vinh Trần** | Từ IT Helpdesk đến Senior Sysadmin – Hành trình sự nghiệp |

---

### Những Nội Dung Nổi Bật Mình Tâm Đắc

#### Talk 1 – Rock Paper Scissors với AWS WebSocket (Multiplayer Real-time)

Anh Bảo đã chia sẻ cách dùng **Godot 4** làm client cho game, kết hợp với kiến trúc serverless hoàn toàn trên AWS:

*   Mình học được cách **API Gateway WebSocket** định tuyến các kết nối thông qua `$connect`, `$disconnect`, `$default`, đồng thời đọc trường `action` trong JSON body để xác định chính xác luồng xử lý của game.
*   **AWS Lambda** đóng vai trò phía sau để xử lý việc ghép cặp người chơi (matchmaking) và tính toán kết quả thắng thua.
*   Anh dùng **Amazon DynamoDB** để lưu lại trạng thái kết nối của từng người chơi, bao gồm `connectionId`, status (`waiting`/`matched`), `opponentId`, và `choice` (búa/bao/kéo).
*   Anh cũng chỉ ra những bài toán hóc búa trong thực tế như:
    *   Lỗi **GoneException** xảy ra khi người chơi đã ngắt kết nối mà DynamoDB vẫn còn lưu dữ liệu, khiến Lambda bị lỗi khi cố gửi tin nhắn.
    *   Vấn đề **DynamoDB Scan cost**: Việc dùng ScanCommand để duyệt toàn bộ bảng rất tốn kém và chậm chạp khi lượng người chơi tăng cao.
    *   Tính chất **Stateless Lambda**: Vì Lambda phi trạng thái nên mỗi lần gọi nó đều phải fetch lại trạng thái game từ DynamoDB.
*   **Giải pháp tiếp theo**: Đối với các tựa game cần server chuyên dụng, có tần suất cập nhật cao hoặc cần mô phỏng vật lý thời gian thực, việc chuyển sang **AWS GameLift** sẽ là phương án tối ưu hơn.

#### Talk 2 – Docker Basics (Ảo hóa & Container hóa)

Diễn giả: **Anh Bảo (Huỳnh Nguyễn Quốc Bảo)** – Junior Cloud Native Developer tại Endava Vietnam, Founder của ITea Lab.

*   Anh giải thích rất trực quan về sự khác biệt giữa **Virtual Machine** (mỗi VM phải cõng một OS riêng nên rất tốn tài nguyên) và **Container** (siêu nhẹ nhờ khả năng dùng chung kernel của host OS).
*   Những khái niệm Docker cốt lõi mình nắm được:
    *   **Dockerfile** dùng để định nghĩa các bước build; mỗi dòng lệnh sẽ sinh ra một **image layer** bất biến — Docker rất thông minh khi biết cách tái sử dụng các layer chưa thay đổi từ cache để ép xung tốc độ build.
    *   **Docker Images** đóng vai trò như một bản thiết kế, còn **Containers** chính là các thực thể (instance) đang chạy thực tế của image đó.
    *   Container hoạt động hoàn toàn độc lập với máy host và được thao tác thông qua Docker CLI.
*   **Ứng dụng thực tế**: Docker cực kỳ hữu dụng cho CI/CD pipelines, kiến trúc microservices, setup môi trường dev/test, làm app cloud-native hay thậm chí là hiện đại hóa các app legacy cũ kỹ.
*   Lợi ích mang lại lớn nhất chính là triết lý *"Build once, run anywhere"* — giúp đảm bảo ứng dụng chạy đồng nhất từ máy dev lên môi trường staging và thẳng tiến production.

#### Talk 3 – GraphRAG (Graph Retrieval Augmented Generation)

Diễn giả: Bạn **Đinh Việt Phát** – Sinh viên chuyên ngành AI tại Swinburne University of Technology.

*   Phát chỉ ra rằng **RAG truyền thống** (truy xuất đoạn văn bản từ vector database rồi đưa vào prompt LLM) thường đuối sức với các câu hỏi đòi hỏi **suy luận đa bước** (chẳng hạn như: "Trụ sở của công ty được mua lại bởi công ty do Jeff Bezos sáng lập ở đâu?").
*   **GraphRAG** ra đời để giải quyết điểm yếu này bằng cách lưu trữ **mối quan hệ giữa các thực thể dưới dạng các cạnh của đồ thị**, qua đó AI có thể duyệt qua hàng loạt thực thể và tài liệu liên kết với nhau.
*   Có hai hướng để anh em triển khai trên AWS:
    *   **Fully Managed Route**: Kết hợp **Amazon Bedrock Knowledge Bases** (lo phần chunking, entity extraction, tạo embeddings) với **Amazon Neptune Analytics** (để lưu trữ đồ thị và khám phá quan hệ).
    *   **Custom Route**: Tự tay build với **LlamaIndex** cho pipeline tùy chỉnh và dùng **Amazon Neptune** để lưu Knowledge Graph, từ đó thực hiện multi-hop traversal cùng Cypher Query.
*   Ưu điểm lớn nhất của GraphRAG là khả năng xử lý mượt mà các câu hỏi phức tạp, đan xen nhiều mối quan hệ mà vector search thuần túy phải bó tay.

#### Talk 4 – AWS WAF & ML-based NIDS

Diễn giả: Bạn **Lê Hoàng Gia Đại** – Sinh viên năm cuối trường Đại học HUTECH.

*   **AWS WAF** là chốt chặn bảo vệ CloudFront, ALB, API Gateway và Cognito qua các Web ACLs và rules (như Allow/Block/Count/CAPTCHA). Nó cực kỳ hiệu quả với các tấn công đã nằm trong blacklist, nhưng lại tỏ ra yếu thế trước các đòn zero-day, hybrid và spoofing attacks.
*   Đại đã demo việc xây dựng **NIDS dựa trên Machine Learning**, sử dụng bộ dataset **CSE-CIC-IDS2018** (từ Đại học New Brunswick), bao phủ các dạng tấn công như: DDoS, DoS, Brute Force, SQL Injection, XSS, Bot traffic....
*   Model được chọn là **LightGBM** — model này được đem đi huấn luyện sau khi trải qua bước tiền xử lý dữ liệu kỹ lưỡng (xử lý giá trị NaN/vô cực, cân bằng lớp dữ liệu, chọn lọc đặc trưng).
*   Một bức tranh kiến trúc AWS rất đồ sộ được vẽ ra: **VPC → EC2 → ALB → AWS WAF → Lambda → Kinesis Data Firehose → S3 → Security Hub + GuardDuty + Inspector → SNS alerts → CloudWatch monitoring**.
*   Bài học cốt lõi: Chất lượng của dữ liệu đầu vào mang tính quyết định; việc xử lý class imbalance giúp cải thiện rõ rệt khả năng phát hiện các luồng tấn công thiểu số. Hơn nữa, ML-based NIDS sinh ra là để **bổ sung** sức mạnh cho AWS WAF chứ không hề thay thế nó.

#### Talk 5 – Từ IT Helpdesk đến Senior Sysadmin

Diễn giả: Anh **Trần Trung Vinh** – System Administrator tại Central Retail Group.

*   Anh Vinh chia sẻ về lộ trình nghề nghiệp cực thực tế của mình: Từ IT Helpdesk bước lên Sysadmin rồi tiến tới Cloud/DevOps Engineer.
*   Quãng thời gian làm Helpdesk đã rèn cho anh kỹ năng xử lý sự cố dưới áp lực cao, cách giao tiếp mềm mỏng với người dùng và rèn luyện tư duy giải quyết vấn đề.
*   Công việc hàng ngày của một Sysadmin xoay quanh provisioning server, quản lý hạ tầng mạng lưới, vá lỗi bảo mật và lên kế hoạch dung lượng hệ thống.
    *   Anh nhấn mạnh một **Quy tắc vàng**: *"Không bao giờ test trên production — phải luôn bảo vệ tính khả dụng, niềm tin và thời gian của cả team"*.
*   Khi chuyển dịch sang mảng Cloud/DevOps: Anh đã thay đổi tư duy từ việc cấu hình thủ công on-premise sang sử dụng **AWS elastic scaling**, áp dụng **Terraform** (IaC), xây dựng **CI/CD pipelines** và ứng dụng **Docker**.
*   Kinh nghiệm xương máu khi đi phỏng vấn tại Central Retail Group: Nhà tuyển dụng cực kỳ chú trọng vào các dự án thực tế, kỹ năng xử lý sự cố nhạy bén và tư duy thiết kế kiến trúc.
*   Lời khuyên nghề nghiệp từ anh:
    *   *Hãy đào thật sâu vào 1–2 lĩnh vực cốt lõi trước khi định mở rộng sang cái khác*.
    *   *Một portfolio chứa các dự án thực tế có sức nặng hơn rất nhiều so với những tờ giấy chứng chỉ*.
    *   *Xuất phát điểm của bạn ở đâu không quan trọng — quan trọng là hãy tiếp tục tiến lên. Mỗi một bước chân nhỏ đều có ý nghĩa của nó.*.

---

### Những Gì Mình Tích Lũy Được

#### Góc Độ Kỹ Thuật

*   **AWS WebSocket + Lambda + DynamoDB**: Mình nắm được combo serverless chuyên trị các ứng dụng real-time turn-based; còn AWS GameLift sẽ là trùm cuối cho các game yêu cầu tần suất cập nhật cao.
*   **Docker layers & caching**: Việc thấu hiểu cách image layers hoạt động sẽ giúp mình viết Dockerfile mượt mà hơn và ép xung tối đa cho CI/CD pipeline.
*   **GraphRAG vs. RAG**: Rất thú vị khi biết GraphRAG dùng Amazon Neptune để lưu trữ quan hệ thực thể dưới dạng các cạnh đồ thị, từ đó AI có thể suy luận đa bước – một khả năng mà vector search thuần túy phải chào thua.
*   **ML ứng dụng trong bảo mật**: Sự kết hợp giữa LightGBM-based NIDS và AWS WAF tạo nên một bức tường phòng thủ linh hoạt — quy tắc signature để chặn các mối đe dọa cũ, còn ML để đánh hơi các mối đe dọa mới.
*   **Infrastructure as Code**: Giờ thì mình đã hiểu tại sao Terraform lại thần thánh đến vậy trong việc giúp hạ tầng cloud tái sử dụng được, dễ dàng kiểm soát phiên bản và mở rộng.

#### Góc Độ Nghề Nghiệp & Tư Duy

*   **Chuyển đổi nghề nghiệp là điều hoàn toàn khả thi** miễn là chúng ta có một lộ trình đúng đắn và tinh thần học hỏi không mệt mỏi — câu chuyện của anh Vinh Trần là một minh chứng sống động.
*   Việc lao vào làm **các dự án thực tế** (như tự build một game WebSocket multiplayer) là con đường ngắn nhất để làm chủ các khái niệm cloud.
*   **Học tập cùng cộng đồng** thực sự giúp tăng tốc độ phát triển — việc trao đổi và tiếp thu kiến thức trong một môi trường ngang hàng mang lại hiệu quả vượt sức tưởng tượng.

---

### Kế Hoạch Ứng Dụng Vào Công Việc

*   Sắp tới, mình sẽ bắt tay vào vọc vạch **AWS API Gateway WebSocket + Lambda** để làm các tính năng real-time (như push thông báo hay làm live dashboard).
*   Mình sẽ thực hành viết **Dockerfile sao cho hiệu quả nhất** — tập trung hiểu sâu về layer caching để giảm thời gian build.
*   Chắc chắn mình sẽ tìm hiểu sâu thêm về **GraphRAG với Amazon Bedrock + Neptune** để áp dụng cho các tính năng AI cần xử lý tri thức phức tạp.
*   Trong tương lai, mình sẽ cân nhắc việc mix giữa **AWS WAF và ML-based NIDS** để tạo ra một môi trường production có tính bảo mật thông minh hơn.
*   Quan trọng nhất, mình sẽ xây dựng một **lộ trình học tập cá nhân** rõ ràng — pick ra 1–2 mảng cốt lõi, cày cuốc dự án thực tế, ghi chép lại mọi thứ và mang đi chia sẻ.

---

### Trải Nghiệm Cá Nhân Tại Sự Kiện

Được tham gia **FCAJ Meetup #1** thực sự là một trải nghiệm mở mang tầm mắt đối với mình. Khác hẳn với cái vẻ trang trọng, khô khan của những buổi workshop hay khóa đào tạo thông thường, sự kiện này hừng hực năng lượng của một cộng đồng đam mê, tụ họp lại để cùng nhau học hỏi và chia sẻ.

#### Các bài chia sẻ cực kỳ thực chiến

Mỗi bài trình bày đều được đúc kết từ máu và nước mắt thực chiến — từ việc tự tay build một con game multiplayer trên nền AWS cho đến chặng đường trầy trật đi lên từ anh thợ helpdesk thành senior engineer. Chính điều này làm cho những kiến thức được truyền đạt trở nên cực kỳ gần gũi và có tính ứng dụng rất cao.

#### Chạm tay vào hệ sinh thái AWS

Buổi meetup này đã giúp mình lướt qua một loạt các dịch vụ của AWS — **API Gateway, Lambda, DynamoDB, WAF, Bedrock, Neptune, GuardDuty, Kinesis** — vẽ ra trong đầu mình một bức tranh kiến trúc tổng thể về cách các mảnh ghép này phối hợp với nhau trong thực tế.

#### Khai sáng về AI

Phiên nói chuyện về **GraphRAG** chính là spotlight của buổi tối hôm đó đối với cá nhân mình. Nó hoàn toàn thay đổi tư duy của mình về cách AI truy xuất thông tin — bứt phá khỏi giới hạn của việc tìm kiếm vector phẳng để chạm đến cấp độ trích xuất tri thức dựa trên đồ thị cấu trúc. Việc được nghe phân tích điểm khác biệt giữa luồng Fully Managed (Bedrock + Neptune Analytics) và Custom (LlamaIndex + Neptune) đã vạch ra cho mình một vạch xuất phát cực kỳ rõ ràng để bắt đầu thực hành.

#### Lấy cảm hứng từ những câu chuyện nghề

**Hành trình của anh Vinh Trần** từ một nhân viên IT Helpdesk lên vị trí Senior Sysadmin tại Central Retail Group là một trong những khoảnh khắc truyền cảm hứng nhất đêm đó. Cấu trúc tư duy khi giải quyết sự cố của anh: *hiểu rõ hệ thống, tìm cách giảm thiểu thiệt hại, đào sâu nguyên nhân gốc rễ, và quy tắc sống còn là không bao giờ test trên production* — là hành trang quý giá mà mình sẽ luôn mang theo. Lời chia sẻ của anh đã củng cố niềm tin trong mình rằng: chỉ cần có chiều sâu kỹ thuật, sự kiên trì bền bỉ và một định hướng đúng đắn, bất kỳ ai cũng có thể tiến rất xa trong ngành công nghệ này.

#### Những Bài Học Gói Ghém Mang Về

*   **Làm dự án thực tế mới đem lại bài học thực tế** — bản demo game WebSocket đã chứng minh rành rành rằng lý thuyết chỉ thực sự "sống" khi bạn xắn tay áo lên và build một sản phẩm từ đầu chí cuối.
*   **Sức mạnh của Docker vượt xa những gì mình nghĩ** — việc hiểu về layer caching, deploy trên nhiều nền tảng hay việc kiểm tra container mang lại chiều sâu kiến thức lớn hơn rất nhiều so với khái niệm "đóng gói app" đơn thuần.
*   **Machine Learning là mảnh ghép hoàn hảo cho hệ thống dựa trên quy tắc** — mình nhận ra rằng AWS WAF đứng một mình là chưa đủ; việc ghép đôi nó với ML-based NIDS mới tạo ra được một tấm khiên bảo mật có khả năng thích ứng thực sự.
*   **Cộng đồng chính là chất xúc tác** — việc được hít thở chung một bầu không khí với những anh em đang ngày đêm cày cuốc, xây dựng và phát triển hệ thống tạo ra một luồng năng lượng mạnh mẽ mà mình không bao giờ có thể tìm thấy khi ngồi học online một mình.

#### Một Số Hình Ảnh Khi Tham Gia Sự Kiện

![FCAJ Meetup 1 - ngày 6 tháng 6, 2026](meetup-1.jpg)

> Nhìn chung, FCAJ Meetup là một cú đề-pa đầy nhiệt huyết cho con đường học tập từ cộng đồng của mình. Sự phong phú của các chủ đề — trải dài từ làm game, làm AI cho đến chuyện phát triển sự nghiệp — đã cho mình thấy thế giới Cloud & AI này rộng lớn và đầy ắp những điều thú vị đến nhường nào. Mình bước ra khỏi sự kiện với một cái đầu đầy ý tưởng mới, những người bạn mới và một nguồn động lực to lớn để tiếp tục con đường chinh phục công nghệ.