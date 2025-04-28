---
title: "Ứng dụng phân tán là gì "
date: "2025-04-28"
updated: "2023-04-28"
categories:
  - "sveltekit"
  - "markdown"
coverImage: "https://thafd.bing.com/th/id/OIP.tt7SLo-YeIPvOzQRuKh38gAAAA?rs=1&pid=ImgDetMain"
coverWidth: 16
coverHeight: 9
excerpt: Check out how heading links work with this starter in this post.
---

Hệ thống phân tán (Distributed System) : là một tập hợp các máy tính độc lập, kết nối với nhau qua mạng và phối hợp hành động để đạt được một mục tiêu chung. Mỗi máy tính trong hệ thống đều có bộ nhớ riêng và hệ điều hành riêng, nhưng người dùng hoặc các ứng dụng có thể tương tác với hệ thống như thể đó là một hệ thống thống nhất.

## Các ứng dụng của hệ thống phân tán 
Bạn có thể bắt gặp hệ thống phân tán ở khắp mọi nơi:


- Mạng xã hội: Facebook, Instagram xử lý hàng tỷ lượt đăng tải, bình luận mỗi ngày nhờ vào hệ thống phân tán.

- Thương mại điện tử: Amazon, Shopee đảm bảo đơn hàng được xử lý liên tục, kể cả trong mùa sale cực lớn.

- Dịch vụ streaming: Netflix, YouTube cung cấp nội dung cho hàng triệu người dùng cùng lúc mà vẫn mượt mà.

- Ngân hàng số: Các ứng dụng tài chính phải xử lý giao dịch nhanh chóng và an toàn suốt 24/7.

- Điện toán đám mây: AWS, Azure, Google Cloud — nền tảng cho hàng ngàn ứng dụng hiện đại.

### Các khái niệm chính của ứng dụng phân tán 

Để xây dựng một hệ thống phân tán hiệu quả, các nhà phát triển cần hiểu rõ một số khái niệm cơ bản sau:

- Scalability (Khả năng mở rộng): Đáp ứng nhu cầu tăng trưởng người dùng hoặc dữ liệu.

- Fault Tolerance (Chịu lỗi): Vận hành liên tục ngay cả khi một phần hệ thống gặp sự cố.

- Availability (Tính sẵn sàng): Đảm bảo dịch vụ luôn trực tuyến cho người dùng.

- Transparency (Tính trong suốt): Người dùng không cần quan tâm bên dưới hệ thống hoạt động ra sao.

- Concurrency (Tính đồng thời): Nhiều tiến trình có thể diễn ra cùng lúc.

- Parallelism (Tính song song): Các tác vụ được xử lý đồng thời để tăng hiệu suất.

- Openness (Tính mở): Hệ thống dễ dàng tích hợp với những công nghệ khác.

- Vertical Scaling: Nâng cấp phần cứng cho máy chủ hiện tại (ví dụ: thêm RAM, CPU mạnh hơn).

- Horizontal Scaling: Thêm nhiều máy chủ mới vào hệ thống.

- Load Balancer: Phân phối đều lưu lượng truy cập giữa các máy chủ.

- Replication: Sao chép dữ liệu giữa các máy chủ để tăng độ tin cậy và tốc độ truy xuất.
#### Liên kết các khái niệm qua một ví dụ thực tế
Liên kết các khái niệm qua một ví dụ thực tế
Hãy lấy một trang thương mại điện tử như Shopee làm ví dụ:

- Vào dịp sale lớn, số lượng người truy cập tăng đột biến. Hệ thống cần scalability để thêm nhiều server (horizontal scaling) hoặc nâng cấp server (vertical scaling).

- Nếu một server bất ngờ lỗi, fault tolerance và replication đảm bảo không ai bị gián đoạn trải nghiệm mua sắm.

- Người dùng có thể mua sắm suốt ngày đêm nhờ availability cao.

- Khi bạn tìm kiếm sản phẩm, mua hàng, và chat với người bán cùng lúc, hệ thống phải hỗ trợ concurrency và parallelism để mọi thao tác mượt mà.

- Load balancer sẽ phân bổ các yêu cầu truy cập tới nhiều server, tránh tình trạng nghẽn mạng.

- Toàn bộ trải nghiệm mua sắm diễn ra liền mạch, người dùng không hề biết đằng sau có hàng nghìn máy chủ đang hoạt động — đó chính là transparency.

- Một hệ thống phân tán tốt chính là như vậy: mở rộng dễ dàng, chịu được lỗi, luôn luôn sẵn sàng, và mang đến trải nghiệm người dùng mượt mà.

##### Các kiến trúc phổ biến của hệ thống phân tán
Hệ thống phân tán có thể được xây dựng theo nhiều mô hình kiến trúc khác nhau, tùy thuộc vào nhu cầu:

- Client-Server: Máy khách gửi yêu cầu và nhận dữ liệu từ máy chủ (ví dụ: ứng dụng web truyền thống).

- Three-tier Architecture: Tách biệt giao diện người dùng, xử lý nghiệp vụ, và lưu trữ dữ liệu.

- Peer-to-Peer (P2P): Các nút trong mạng ngang hàng với nhau, không có máy chủ trung tâm (ví dụ: BitTorrent).

- Microservices: Chia hệ thống thành nhiều dịch vụ nhỏ độc lập, dễ dàng triển khai, nâng cấp riêng lẻ.

- Serverless: Không cần quản lý máy chủ vật lý; chỉ viết và triển khai các chức năng.


###### Ví dụ thực tế
Một hệ thống phân tán hiện đại như Netflix sẽ sử dụng:

- Frontend: Giao diện người dùng React hoặc TV apps.

- Backend: Microservices xử lý từng chức năng riêng (như recommendation service, billing service, streaming service).

- Database: NoSQL databases như Cassandra để lưu trữ hàng tỷ bản ghi.

- Load Balancer: Phân phối hàng triệu yêu cầu xem video mỗi phút.

- Serverless Functions: Các tác vụ nhỏ như gửi email xác nhận tài khoản.

