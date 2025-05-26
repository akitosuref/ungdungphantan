---
title: "Ôn tập Cuối kì"
date: "2025-05-25"
updated: "2025-05-25"
author: "Vương quang Quý"
categories:
  - "Distributed Systems"
  - "Processes and Threads"
  - "Concurrency"
coverImage: "https://th.bing.com/th/id/OIP.xqYunaXLEIiIBgbHGncjBQHaHa?cb=iwc2&rs=1&pid=ImgDetMain"
coverWidth: 16
coverHeight: 9
excerpt: ôn tập cuối kì
---
🖧 Tổng Hợp Kiến Thức Hệ Phân Tán (Distributed Systems)
1. Hệ thống phân tán, tập trung, phi tập trung khác nhau như thế nào?
Loại hệ thống	Đặc điểm chính	Ví dụ
Tập trung	Tất cả dữ liệu và xử lý đều tập trung ở một nút trung tâm.	Hệ thống mainframe
Phân tán	Các nút hoạt động độc lập và phối hợp qua mạng.	Hệ thống microservices
Phi tập trung	Không có nút trung tâm rõ ràng, nhưng có tổ chức chia sẻ vai trò.	Blockchain, BitTorrent

Xác định khác biệt chính:
Kiểm tra sự hiện diện của nút trung tâm và mức độ kiểm soát tập trung.

Ứng phó sự cố:

Tập trung: dễ bị sập toàn bộ.

Phân tán & phi tập trung: chịu lỗi tốt hơn.

2. Các đặc tính của hệ phân tán
Tính minh bạch: Ẩn chi tiết hệ thống (vị trí, truy cập, di trú, đồng thời,...)

Khả năng mở rộng: Thêm nút không ảnh hưởng hiệu suất.

Chịu lỗi: Vẫn hoạt động khi có sự cố cục bộ.

Tính đồng thời: Nhiều tác vụ xảy ra đồng thời.

Tính không đồng bộ: Truyền thông không đảm bảo thời gian thực.

Không đồng nhất: Hỗ trợ đa nền tảng (OS, ngôn ngữ,...)

3. Mục đích của nút chủ trong hệ phân tán
Quản lý, điều phối hoạt động chung.

Phân phối tài nguyên.

Xác thực và cấp quyền.

Nếu nút chủ gặp sự cố:
-> Dẫn đến gián đoạn dịch vụ hoặc cần có cơ chế thay thế (ví dụ: election trong Bully algorithm).

4. Giao tiếp gossip protocol
Tại sao không gửi toàn bộ? Tránh quá tải mạng, tăng khả năng mở rộng.

Không dùng trung tâm: Vì dễ bị tắc nghẽn hoặc trở thành điểm lỗi.

5. Yếu tố cốt lõi của hệ phân tán
Đồng bộ hóa

Truyền thông

Quản lý tài nguyên phân tán

Chịu lỗi

Bảo mật

6. Lý do sử dụng hệ phân tán
Hiệu năng cao

Mở rộng linh hoạt

Chịu lỗi tốt

Đáp ứng địa lý (phân phối toàn cầu)

Tận dụng tài nguyên rảnh rỗi

7. Định nghĩa hệ phân tán
Hệ phân tán là tập hợp các máy tính độc lập, hiển thị với người dùng như một hệ thống thống nhất.

8. Hình ảnh cần chụp và đưa lên blog
Cristian algorithm

Berkeley algorithm

RBS (Reference Broadcast Synchronization)

Lamport clock

Bully algorithm

Ring algorithm

9. Kỹ thuật phân tán hỗ trợ
Mục tiêu	Kỹ thuật hỗ trợ
Lập trình thủ tục	RPC (Remote Procedure Call)
Lập trình web	Web services, REST, SOAP
Hướng đối tượng	RMI (Remote Method Invocation)

10. Tiến trình nhẹ, tiến trình, luồng
Loại	Ưu điểm	Nhược điểm
Tiến trình nhẹ (lightweight process)	Tạo nhanh, tiêu tốn ít tài nguyên	Chia sẻ bộ nhớ nên dễ lỗi
Tiến trình (process)	Cô lập tốt	Tốn tài nguyên hơn
Luồng (thread)	Chia sẻ bộ nhớ, giao tiếp nhanh	Khó kiểm soát đồng bộ

Khi lỗi hệ thống xảy ra:

Tiến trình nhẹ và luồng có thể gây sập toàn bộ tiến trình chính.

Tiến trình riêng biệt ít bị ảnh hưởng lẫn nhau.

Mối quan hệ:

Một tiến trình có thể chứa nhiều luồng.

11. Mô hình Client - Server
Client: Gửi yêu cầu.

Server: Xử lý và trả lời yêu cầu.

12. Gọi thủ tục từ xa (RPC)
Cho phép một chương trình gọi hàm nằm trên máy khác như thể cục bộ.

13. Mô hình phân tầng giao thức & hướng thông điệp
Mục đích: Tách biệt vai trò, tăng tái sử dụng.

Lợi ích: Bảo trì dễ dàng, thay đổi tầng không ảnh hưởng tầng khác.

14. Sharding là gì?
Sharding là chia dữ liệu lớn thành các phần nhỏ hơn (shard) để lưu trữ trên nhiều máy.

15. Gói luồng có thể làm gì?
Xử lý song song

Quản lý kết nối nhiều client

Tăng hiệu năng hệ thống

16. Luồng kiểu người dùng vs kiểu nhân
Loại luồng	Đặc điểm
Người dùng	Quản lý bởi user-level thư viện
Nhân	Quản lý bởi hệ điều hành

17. Các hàm chính trong RPC
register(): đăng ký hàm từ xa

call(): gọi hàm từ xa

return(): trả về kết quả

bind(): liên kết client/server

18. Định nghĩa
Tiến trình (Process): chương trình đang chạy.

Luồng (Thread): đơn vị nhỏ hơn tiến trình.

Multithread Client/Server: client/server hỗ trợ nhiều luồng để xử lý đồng thời.

19. MapReduce
Map: chia nhỏ công việc.

Reduce: tổng hợp kết quả.

Mục đích: xử lý dữ liệu lớn song song trong hệ phân tán.

20. Ảo hóa (Virtualization)
Tạo máy ảo trên phần cứng thật.

Mục đích: Tối ưu tài nguyên, cách ly môi trường, dễ mở rộng.

21. Kiến trúc server đa luồng
Một server tạo nhiều luồng để phục vụ nhiều client cùng lúc.

22. Cài đặt luồng
Thread pool

Fork-per-request

Event-driven với I/O không đồng bộ

23. Bảng băm phân tán
Mục đích: phân phối dữ liệu đều trên các nút.

Consistent Hashing: thay đổi số nút ít ảnh hưởng dữ liệu.

Finger table: hỗ trợ tìm kiếm nhanh hơn (như trong Chord).

24. Không gian phẳng & định danh
Không gian phẳng: không có cấu trúc thứ bậc.

Định danh: chuỗi duy nhất định danh tài nguyên.

Đặc điểm: độc lập, không trùng, không phụ thuộc vị trí.

25. Đồng bộ hóa đồng hồ
Đồng hồ vật lý không đảm bảo vì độ lệch.

Mục đích: đảm bảo thứ tự sự kiện.

Thuật toán: Cristian, Berkeley, Lamport clock,...

26. Đồng hồ Lamport
Giải quyết: thứ tự xảy ra của sự kiện trong hệ phân tán.

Quy tắc:

Mỗi sự kiện tăng đồng hồ.

Khi gửi/nhận: so sánh và cập nhật.

27. Bài tập đồng hồ Lamport
Xem slides chương 4 - 5, làm các bài gán thời gian Lamport, vector clock.

28. Giao thức đồng bộ
NTP (Network Time Protocol): dựa vào client-server, tính độ trễ.

PTP (Precision Time Protocol): chính xác hơn, dùng trong mạng LAN, yêu cầu phần cứng hỗ trợ.