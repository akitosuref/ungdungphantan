---
title: "Weekend 2"
date: "2025-05-05"
updated: "2025-05-05"
categories:
  - "sveltekit"
  - "markdown"
  - "svelte"
coverImage: "/images/jerry-zhang-ePpaQC2c1xA-unsplash.jpg"
coverWidth: 16
coverHeight: 9
excerpt: This post demonstrates how to include a Svelte component in a Markdown post.
---

<script>
	import Callout from '$lib/components/Callout.svelte';
</script>

#### Câu 1 Check CPU , GPU , RAM , Giải thích về hiệu năng của máy tính mà em  đang dùng ?
**CPU có** : + cores : 10 
         + Logical processors : 12
         + tốc độ xung nhịp ~1.3 GHz
         + kiến trúc : Intel CORE 5
GPU có : Intel (R) UHD Graphics ~ 1%
Ram :8192 MB RAM
##### Giải thích hiệu năng của máy theo từng thông số :
**Phân tích hiệu năng của CPU:**

- **Số lõi và luồng:** CPU có 10 lõi và 12 luồng, giúp xử lý đa nhiệm tốt và cải thiện hiệu suất khi chạy nhiều chương trình cùng lúc.
- **Tốc độ xung nhịp:** Với tốc độ ~1.3 GHz, đây là một tốc độ khá thấp so với các dòng CPU cao cấp (2.5 GHz - 4.0 GHz).
- **Kiến trúc:** Intel Core i5 thuộc dòng CPU trung cấp, cung cấp hiệu suất tốt cho các công việc văn phòng, lập trình, và các ứng dụng đa nhiệm cơ bản.

**=> Kết luận hiệu năng:** 
CPU này có thể xử lý đa nhiệm và các tác vụ tính toán tốt, nhưng khi xử lý các tác vụ nặng như chơi game 3D hoặc render video, tốc độ xung nhịp thấp có thể ảnh hưởng đến hiệu suất.

**Phân tích hiệu năng của GPU :**

- **GPU tích hợp (Intel UHD Graphics):** Là GPU tích hợp với CPU, có khả năng xử lý các tác vụ đồ họa cơ bản như xem video HD, duyệt web, hoặc chơi game nhẹ.
- **Tỷ lệ sử dụng:** GPU này chiếm khoảng 1% tài nguyên, cho thấy rằng nó không được sử dụng nhiều trong các tác vụ cơ bản.

**=>Hiệu năng:** 
Intel UHD Graphics đủ để xử lý các tác vụ đồ họa nhẹ, nhưng không đủ mạnh cho các ứng dụng yêu cầu đồ họa phức tạp hoặc chơi game 3D. Nếu cần xử lý đồ họa nặng, một GPU rời sẽ phù hợp hơn.

**Phân tích hiệu năng của RAM**
**Ứng dụng nặng:** Nếu làm việc với các ứng dụng yêu cầu nhiều bộ nhớ như máy ảo hoặc chỉnh sửa video, bạn sẽ cần ít nhất 16GB RAM để đảm bảo hiệu suất mượt mà hơn.

**=>Hiệu năng:**
Với 8GB RAM, máy tính của sẽ xử lý đa nhiệm khá tốt trong các công việc văn phòng và các tác vụ thông thường. Tuy nhiên, nếu làm việc với các ứng dụng nặng hoặc chạy nhiều tác vụ đồng thời, RAM có thể trở thành yếu tố hạn chế.
#### Câu 2 Nghiên cứu tìm hiểu, liệt kê ít nhất 12 bài toán phổ biến trong ngành CNTT của em đang học, những bài toán này sử dụng đa luồng, đa tiến trình ở đâu

