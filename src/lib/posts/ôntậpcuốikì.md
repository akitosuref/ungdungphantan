---
title: "Ôn tập Cuối kì Hệ Phân Tán"
date: "2025-05-29"
updated: "2025-05-29"
author: "Vương Quang Quý"
categories:
  - "Distributed Systems"
  - "Processes and Threads"
  - "Concurrency"
coverImage: "https://th.bing.com/th/id/OIP.xqYunaXLEIiIBgbHGncjBQHaHa?cb=iwc2&rs=1&pid=ImgDetMain"
coverWidth: 16
coverHeight: 9
excerpt: Tổng hợp 28 câu hỏi ôn tập cuối kì môn Hệ Phân Tán, trình bày chuẩn tác phong sinh viên.
---

# ÔN TẬP CUỐI KÌ MÔN HỆ PHÂN TÁN

> **Tác giả:** Vương Quang Quý  
> **Ngày cập nhật:** 29/05/2025  
> **Chuyên mục:** Distributed Systems, Processes and Threads, Concurrency

---

## MỤC LỤC

1. Hệ thống phân tán, tập trung, phi tập trung khác nhau như thế nào? Nêu ví dụ về mỗi loại, làm thế nào để xác định sự khác biệt chính?
2. Các đặc tính của hệ phân tán là gì? Giải thích cho từng đặc điểm thật kỹ.
3. Mục đích của nút chủ trong một hệ phân tán là gì? Điều gì sẽ xảy ra nếu nút chủ gặp sự cố?
4. Trong một mạng không gian, tại sao các máy thường giao tiếp với nhau qua gossip protocol mà không gửi thông tin đến tất cả các máy khác hoặc gửi về một nút trung tâm?
5. Các yếu tố cốt lõi của một hệ phân tán là gì?
6. Nêu những lý do sử dụng hệ phân tán.
7. Định nghĩa hệ phân tán.
8. Chụp và để lên blog các hình của thuật toán Cristian, Berkeley, RBS, Lamport, Bully, Ring.
9. Kỹ thuật phân tán nào hỗ trợ lập trình thủ tục, lập trình web, hướng đối tượng? Liệt kê.
10. Tiến trình nhẹ, tiến trình, luồng có những ưu điểm và nhược điểm gì? Khi một lời gọi hệ thống dừng thì đối với 3 loại như thế nào? Tiến trình nhẹ, tiến trình và luồng có mối quan hệ như thế nào với nhau và với chính nó?
11. Mô hình client-server là gì? Vai trò của máy chủ và máy khách là gì?
12. Quá trình gọi thủ tục từ xa là gì?
13. Nêu mục đích và lợi ích của mô hình phân tầng giao thức, hướng thông điệp bền vững.
14. Sharding là gì?
15. Các gói luồng có thể làm những nhiệm vụ gì?
16. Phân loại sự khác nhau giữa luồng kiểu người dùng và luồng kiểu nhân.
17. Nêu các hàm chính ở trong RPC và giải thích chức năng của nó.
18. Định nghĩa tiến trình, thread, multithread client, multithread server.
19. Review lại kiến thức căn bản của Map, Reduce và mục đích trong một hệ phân tán.
20. Ảo hóa (Virtualization) là gì, mục đích của ảo hóa trong một hệ phân tán dùng để làm gì?
21. Review lại các kiến trúc của server đa luồng.
22. Review lại các hướng tiếp cận cài đặt luồng.
23. Tại sao chúng ta sử dụng bảng băm phân tán, mục đích của bảng băm phân tán là gì, Consistent Hashing là gì, Finger table để làm gì, tại sao sử dụng finger table?
24. Không gian phẳng là gì, định danh là gì, liệt kê các đặc điểm của không gian phẳng.
25. Tại sao cần đồng bộ hóa đồng hồ logic, tại sao đồng hồ vật lý không đảm bảo, mục đích của đồng bộ hóa và các thuật toán đồng bộ hóa là gì?
26. Đồng hồ Lamport giải quyết vấn đề gì, nêu và giải thích các rules của đồng hồ Lamport.
27. Tham khảo lại các bài tập của đồng hồ logic Lamport trong slides chương 4-5.
28. Giao thức đồng bộ NTP là gì, PTP là gì, được tính toán như thế nào?

---

## 1. Hệ thống phân tán, tập trung, phi tập trung khác nhau như thế nào? Nêu ví dụ về mỗi loại, làm thế nào để xác định sự khác biệt chính?

**Hệ thống tập trung:**  
- Tất cả dữ liệu, xử lý và điều khiển tập trung tại một máy chủ duy nhất.  
- Nếu máy chủ gặp sự cố, toàn bộ hệ thống ngừng hoạt động.
- **Ví dụ:** Hệ thống ngân hàng truyền thống, máy chủ web đơn lẻ.

**Hệ thống phân tán:**  
- Nhiều máy tính độc lập, kết nối mạng, phối hợp thực hiện nhiệm vụ chung.
- Các thành phần có thể nằm ở nhiều vị trí địa lý khác nhau, chia sẻ tài nguyên, dữ liệu.
- Nếu một nút bị lỗi, hệ thống vẫn có thể hoạt động (chịu lỗi).
- **Ví dụ:** Google, Facebook, hệ thống đặt vé máy bay.

**Hệ thống phi tập trung:**  
- Không có điểm trung tâm, mọi nút đều bình đẳng, tự chủ, không có máy chủ điều phối chung.
- Quyết định được phân tán, không ai kiểm soát toàn bộ hệ thống.
- **Ví dụ:** Blockchain, BitTorrent, mạng ngang hàng (P2P).

**Cách xác định sự khác biệt chính:**  
- Xem xét điểm kiểm soát trung tâm, cách phân phối dữ liệu, quyền hạn các nút, khả năng chịu lỗi, mức độ phụ thuộc vào một nút duy nhất.

---

## 2. Các đặc tính của hệ phân tán là gì? Giải thích cho từng đặc điểm thật kỹ.

- **Tính minh bạch (Transparency):** Người dùng không nhận ra sự tồn tại của nhiều máy, ẩn đi các chi tiết về vị trí, truy cập, di trú, đồng thời, nhân bản, lỗi, mở rộng.
- **Khả năng mở rộng (Scalability):** Hệ thống có thể mở rộng về số lượng nút, dung lượng lưu trữ, khả năng xử lý mà không làm giảm hiệu năng.
- **Chịu lỗi (Fault Tolerance):** Hệ thống vẫn tiếp tục hoạt động khi một số thành phần bị lỗi nhờ cơ chế dự phòng, phát hiện và phục hồi lỗi.
- **Tính đồng thời (Concurrency):** Nhiều tiến trình hoặc người dùng có thể truy cập và thao tác đồng thời trên hệ thống mà không gây xung đột.
- **Tính không đồng bộ (Asynchrony):** Các thành phần giao tiếp không cần đồng bộ thời gian thực, có thể gửi/nhận thông điệp bất cứ lúc nào.
- **Không đồng nhất (Heterogeneity):** Hỗ trợ nhiều loại phần cứng, hệ điều hành, mạng, ngôn ngữ lập trình khác nhau.
- **Tính mở (Openness):** Hệ thống dễ dàng tích hợp, mở rộng, chuẩn hóa giao tiếp.
- **Bảo mật (Security):** Đảm bảo an toàn dữ liệu, xác thực, phân quyền truy cập trong môi trường phân tán.

---

## 3. Mục đích của nút chủ trong một hệ phân tán là gì? Điều gì sẽ xảy ra nếu nút chủ gặp sự cố?

- **Mục đích:** Nút chủ (master node) quản lý, điều phối hoạt động chung, phân phối tài nguyên, xác thực và cấp quyền cho các nút khác, giữ vai trò trung tâm trong một số thuật toán (ví dụ: election, phân phối khóa).
- **Nếu nút chủ gặp sự cố:**  
  - Dịch vụ bị gián đoạn, các nút khác không thể phối hợp.
  - Cần có cơ chế thay thế nút chủ (ví dụ: thuật toán Bully, Ring) để bầu chọn nút chủ mới, đảm bảo hệ thống tiếp tục hoạt động.

---

## 4. Trong một mạng không gian, tại sao các máy thường giao tiếp với nhau qua gossip protocol mà không gửi thông tin đến tất cả các máy khác hoặc gửi về một nút trung tâm?

- **Gossip protocol** là giao thức truyền tin kiểu "đồn đại", mỗi nút chỉ gửi thông tin cho một số nút ngẫu nhiên, các nút này lại tiếp tục lan truyền thông tin.
- **Lý do sử dụng:**
  - Tránh quá tải mạng khi số lượng nút lớn (không broadcast toàn mạng).
  - Không phụ thuộc vào nút trung tâm, tránh điểm lỗi duy nhất.
  - Đảm bảo thông tin lan truyền nhanh, hiệu quả, tăng khả năng mở rộng và chịu lỗi.

---

## 5. Các yếu tố cốt lõi của một hệ phân tán là gì?

- **Đồng bộ hóa (Synchronization):** Đảm bảo thứ tự và nhất quán dữ liệu, sự kiện giữa các nút.
- **Truyền thông (Communication):** Các nút trao đổi thông điệp, dữ liệu qua mạng.
- **Quản lý tài nguyên phân tán:** Phân phối, chia sẻ, truy cập tài nguyên (CPU, bộ nhớ, dữ liệu) giữa các nút.
- **Chịu lỗi (Fault Tolerance):** Hệ thống tiếp tục hoạt động khi có lỗi cục bộ.
- **Bảo mật (Security):** Bảo vệ dữ liệu, xác thực, phân quyền truy cập.

---

## 6. Nêu những lý do sử dụng hệ phân tán.

- **Tăng hiệu năng:** Chia nhỏ công việc, xử lý song song trên nhiều máy.
- **Khả năng mở rộng:** Dễ dàng thêm bớt tài nguyên, đáp ứng nhu cầu lớn.
- **Chịu lỗi tốt:** Nếu một nút hỏng, hệ thống vẫn hoạt động.
- **Đáp ứng địa lý:** Phục vụ người dùng ở nhiều nơi, giảm độ trễ.
- **Tận dụng tài nguyên rảnh rỗi:** Sử dụng hiệu quả các máy tính nhàn rỗi.

---

## 7. Định nghĩa hệ phân tán.

> Hệ phân tán là tập hợp các máy tính độc lập, phối hợp với nhau thông qua mạng, hiển thị với người dùng như một hệ thống thống nhất.

---

## 8. Chụp và để lên blog các hình của thuật toán Cristian, Berkeley, RBS, Lamport, Bully, Ring.

- **Cristian algorithm:**
  ![Cristian](../../static/images/Cristian%20algorithm.png)
- **Berkeley algorithm:**
  ![Berkeley](../../static/images/Berkeley%20algorithm.jpeg)
- **RBS (Reference Broadcast Synchronization):**
  ![RBS](../../static/images/Comparison-of-a-traditional-synchronization-system-with-RBS.png)
- **Lamport clock:**
  ![Lamport](../../static/images/Lamports-logical-clock.ppm)
- **Bully algorithm:**
  ![Bully](../../static/images/Bully%20algorithm.jpeg)
- **Ring algorithm:**
  ![Ring](../../static/images/Ring%20algorithm.jpeg)

---

## 9. Kỹ thuật phân tán nào hỗ trợ lập trình thủ tục, lập trình web, hướng đối tượng? Liệt kê.

| Mục tiêu                | Kỹ thuật hỗ trợ                  | Giải thích |
|-------------------------|----------------------------------|------------|
| Lập trình thủ tục        | RPC (Remote Procedure Call)      | Cho phép gọi hàm từ xa như cục bộ |
| Lập trình web           | Web services, REST, SOAP         | Giao tiếp qua HTTP, XML/JSON |
| Hướng đối tượng         | RMI (Remote Method Invocation)   | Gọi phương thức đối tượng từ xa |

---

## 10. Tiến trình nhẹ, tiến trình, luồng có những ưu điểm và nhược điểm gì? Khi một lời gọi hệ thống dừng thì đối với 3 loại như thế nào? Tiến trình nhẹ, tiến trình và luồng có mối quan hệ như thế nào với nhau và với chính nó?

| Loại                          | Ưu điểm                        | Nhược điểm                     |
|-------------------------------|--------------------------------|-------------------------------|
| Tiến trình nhẹ (LWP)           | Tạo nhanh, ít tài nguyên, chuyển đổi ngữ cảnh nhanh | Chia sẻ bộ nhớ, dễ lỗi đồng bộ, lỗi một luồng ảnh hưởng toàn bộ tiến trình |
| Tiến trình (Process)           | Cô lập tốt, an toàn, lỗi tiến trình này không ảnh hưởng tiến trình khác | Tốn tài nguyên, chuyển đổi ngữ cảnh chậm, giao tiếp phức tạp |
| Luồng (Thread)                 | Chia sẻ bộ nhớ, giao tiếp nhanh, thích hợp xử lý song song | Khó kiểm soát đồng bộ, dễ tranh chấp tài nguyên, lỗi một luồng ảnh hưởng tiến trình |

- **Khi một lời gọi hệ thống dừng:**
  - Tiến trình: các tiến trình khác vẫn chạy bình thường.
  - Luồng: nếu luồng chính dừng, các luồng con cũng dừng; nếu luồng con dừng, tiến trình vẫn tồn tại.
  - Tiến trình nhẹ: phụ thuộc vào hệ điều hành, thường giống luồng.
- **Mối quan hệ:** Một tiến trình có thể chứa nhiều luồng; tiến trình nhẹ là khái niệm trung gian giữa tiến trình và luồng.

---

## 11. Mô hình client-server là gì? Vai trò của máy chủ và máy khách là gì?

- **Client:** Gửi yêu cầu dịch vụ, nhận kết quả.
- **Server:** Nhận yêu cầu, xử lý và trả kết quả cho client.
- **Ý nghĩa:** Phân chia vai trò rõ ràng, dễ mở rộng, bảo trì.

---

## 12. Quá trình gọi thủ tục từ xa là gì?

- **Gọi thủ tục từ xa (RPC):** Cho phép một chương trình gọi hàm nằm trên máy khác như thể gọi hàm cục bộ.  
- **Quy trình:** Client gửi yêu cầu -> Server thực thi -> Server trả kết quả về client.

---

## 13. Nêu mục đích và lợi ích của mô hình phân tầng giao thức, hướng thông điệp bền vững.

- **Mục đích:** Tách biệt vai trò, tăng tái sử dụng, dễ bảo trì, thay đổi tầng này không ảnh hưởng tầng khác.
- **Lợi ích:** Dễ mở rộng, chuẩn hóa giao tiếp, tăng tính linh hoạt, dễ kiểm thử.

---

## 14. Sharding là gì?

- **Sharding:** Chia nhỏ dữ liệu thành các phần (shard), lưu trữ trên nhiều máy khác nhau để tăng hiệu năng, khả năng mở rộng, giảm tải cho từng máy.

---

## 15. Các gói luồng có thể làm những nhiệm vụ gì?

- Xử lý song song nhiều tác vụ.
- Quản lý kết nối đồng thời từ nhiều client.
- Tăng hiệu năng, giảm thời gian chờ.
- Phân phối tài nguyên hợp lý.

---

## 16. Phân loại sự khác nhau giữa luồng kiểu người dùng và luồng kiểu nhân.

| Loại luồng   | Đặc điểm                        | Ưu điểm | Nhược điểm |
|--------------|---------------------------------|---------|------------|
| Người dùng   | Quản lý bởi thư viện người dùng | Tạo/hủy nhanh, không cần kernel | Nếu 1 luồng bị block, cả tiến trình bị block |
| Nhân         | Quản lý bởi hệ điều hành        | Kernel quản lý, hỗ trợ đa lõi tốt | Tạo/hủy chậm hơn, tốn tài nguyên hơn |

---

## 17. Nêu các hàm chính ở trong RPC và giải thích chức năng của nó.

- `register()`: Đăng ký hàm từ xa để client có thể gọi.
- `call()`: Gửi yêu cầu gọi hàm từ xa.
- `return()`: Nhận kết quả trả về từ server.
- `bind()`: Liên kết client với server.

---

## 18. Định nghĩa tiến trình, thread, multithread client, multithread server.

- **Tiến trình (Process):** Chương trình đang chạy, có không gian địa chỉ riêng.
- **Luồng (Thread):** Đơn vị thực thi nhỏ nhất trong tiến trình, chia sẻ tài nguyên với các luồng khác cùng tiến trình.
- **Multithread client/server:** Client/server có nhiều luồng để xử lý đồng thời nhiều yêu cầu.

---

## 19. Review lại kiến thức căn bản của Map, Reduce và mục đích trong một hệ phân tán.

- **Map:** Chia nhỏ công việc thành các phần nhỏ, xử lý song song.
- **Reduce:** Tổng hợp kết quả từ các phần nhỏ thành kết quả cuối cùng.
- **Mục đích:** Xử lý dữ liệu lớn, tăng tốc độ, tận dụng tài nguyên phân tán.

---

## 20. Ảo hóa (Virtualization) là gì, mục đích của ảo hóa trong một hệ phân tán dùng để làm gì?

- **Ảo hóa:** Tạo ra nhiều máy ảo trên cùng một phần cứng vật lý.
- **Mục đích:** Tối ưu tài nguyên, cách ly môi trường, dễ mở rộng, phục hồi nhanh khi có sự cố.

---

## 21. Review lại các kiến trúc của server đa luồng.

- **Thread-per-connection:** Mỗi kết nối tạo một luồng riêng.
- **Thread pool:** Sử dụng một nhóm luồng cố định để xử lý nhiều kết nối.
- **Event-driven:** Một luồng chính xử lý nhiều kết nối bằng I/O không đồng bộ.

---

## 22. Review lại các hướng tiếp cận cài đặt luồng.

- **Thread pool:** Tạo sẵn một nhóm luồng, tái sử dụng cho nhiều tác vụ.
- **Fork-per-request:** Mỗi yêu cầu tạo một tiến trình/luồng mới.
- **Event-driven:** Sử dụng sự kiện và callback để xử lý nhiều tác vụ không đồng bộ.

---

## 23. Tại sao chúng ta sử dụng bảng băm phân tán, mục đích của bảng băm phân tán là gì, Consistent Hashing là gì, Finger table để làm gì, tại sao sử dụng finger table?

- **Bảng băm phân tán:** Phân phối dữ liệu đều trên các nút, tránh quá tải.
- **Consistent Hashing:** Khi thêm/bớt nút, chỉ một phần nhỏ dữ liệu bị di chuyển, tăng hiệu quả.
- **Finger table:** Bảng tra cứu nhanh trong các hệ thống như Chord, giúp tìm kiếm dữ liệu nhanh hơn.
- **Lý do sử dụng finger table:** Giảm số bước tìm kiếm, tăng hiệu năng truy vấn.

---

## 24. Không gian phẳng là gì, định danh là gì, liệt kê các đặc điểm của không gian phẳng.

- **Không gian phẳng:** Không có cấu trúc thứ bậc, mọi định danh ngang hàng.
- **Định danh:** Chuỗi duy nhất định danh tài nguyên.
- **Đặc điểm:** Độc lập, không trùng, không phụ thuộc vị trí, dễ mở rộng.

---

## 25. Tại sao cần đồng bộ hóa đồng hồ logic, tại sao đồng hồ vật lý không đảm bảo, mục đích của đồng bộ hóa và các thuật toán đồng bộ hóa là gì?

- **Đồng hồ vật lý** không đảm bảo vì có sai số, độ trễ mạng, không đồng bộ tuyệt đối.
- **Đồng bộ hóa đồng hồ logic:** Đảm bảo thứ tự sự kiện, nhất quán dữ liệu.
- **Mục đích:** Xác định quan hệ nhân quả giữa các sự kiện.
- **Thuật toán:** Cristian, Berkeley, Lamport clock, vector clock.

---

## 26. Đồng hồ Lamport giải quyết vấn đề gì, nêu và giải thích các rules của đồng hồ Lamport.

- **Giải quyết:** Thứ tự xảy ra của sự kiện trong hệ phân tán, xác định quan hệ nhân quả.
- **Quy tắc:**
  1. Mỗi sự kiện nội bộ tăng đồng hồ lên 1.
  2. Khi gửi thông điệp, gửi kèm giá trị đồng hồ.
  3. Khi nhận thông điệp, cập nhật đồng hồ bằng max(đồng hồ hiện tại, đồng hồ nhận được) + 1.

---

## 27. Tham khảo lại các bài tập của đồng hồ logic Lamport trong slides chương 4-5.

- Làm các bài tập gán thời gian Lamport, vector clock, xác định thứ tự sự kiện, quan hệ nhân quả.

---

## 28. Giao thức đồng bộ NTP là gì, PTP là gì, được tính toán như thế nào?

- **NTP (Network Time Protocol):** Giao thức đồng bộ thời gian qua Internet, dựa trên mô hình client-server, tính toán độ trễ truyền tin để hiệu chỉnh thời gian.
- **PTP (Precision Time Protocol):** Giao thức đồng bộ thời gian chính xác cao, dùng trong mạng LAN, yêu cầu phần cứng hỗ trợ, độ chính xác cao hơn NTP.
