---
title: "Định danh"
date: "2025-05-02"
updated: "2025-05-12"
author: "Vương Quang QUý"
categories:
  - "Distributed Systems"
  - "Processes and Threads"
  - "Concurrency"
coverImage: "/images/dinhdanh.png"
coverWidth: 16
coverHeight: 9
excerpt: Định danh trong hệ thống phân tán là phương pháp gán tên hoặc ID cho các nút, tài nguyên hoặc dịch vụ, giúp chúng có thể được xác định và truy cập một cách hiệu quả trong môi trường mạng phân tán.
---
# Bài Tập 1: Tìm Hiểu Quy Trình Duyệt Một Trang Web
![cau1](/images/dinhdanh.jpg)

![cau1](/images/dinhdanh2.jpg)




# Bài Tập 2: Thuật Toán Chord

## Giới Thiệu về Chord
Chord là một thuật toán phân tán để tìm kiếm và truy cập dữ liệu trong một mạng peer-to-peer (P2P). Nó sử dụng cấu trúc vòng tròn để tổ chức các nút, cho phép tìm kiếm dữ liệu một cách hiệu quả.

## Ví Dụ Cụ Thể về Chord
Giả sử chúng ta có một mạng P2P với các nút có ID từ 0 đến 7. Nếu một nút muốn tìm dữ liệu có ID là 3, nó sẽ sử dụng thuật toán Chord để tìm kiếm một cách hiệu quả.

## Code Thực Nghiệm

### Cài Đặt Thư Viện
Trước tiên, bạn cần cài đặt thư viện `hashlib` để mã hóa:

```bash
pip install hashlib

import hashlib

class Node:
    def __init__(self, identifier):
        self.id = identifier
        self.data = {}

    def store_data(self, key, value):
        self.data[key] = value

    def find_data(self, key):
        return self.data.get(key, None)

def hash_key(key):
    return int(hashlib.sha1(key.encode()).hexdigest(), 16) % 8

# Ví dụ sử dụng
node1 = Node(1)
node2 = Node(2)

node1.store_data(hash_key("data1"), "value1")
print(node1.find_data(hash_key("data1")))  # Kết quả: value1
```
Dưới đây là một test case cho thuật toán Chord:
```bash
python

def test_chord():
    node = Node(1)
    node.store_data(hash_key("test_key"), "test_value")
    assert node.find_data(hash_key("test_key")) == "test_value"
    assert node.find_data(hash_key("non_existent_key")) is None

test_chord()
print("Tất cả test case đã chạy thành công!")
```