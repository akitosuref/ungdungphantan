---
title: "Trao đổi thông tin"
date: "2025-07-05"
updated: "2023-07-05"
categories:
  - "sveltekit"
  - "web"
  - "css"
  - "markdown"
coverImage: "https://vietquality.vn/wp-content/uploads/2020/05/1_sU6PThU3iIMFVj-6htQdkA.jpeg"
coverWidth: 16
coverHeight: 9
excerpt: Trao đổi thông tin d
---
# 📨 Báo cáo & Demo: Hệ thống truyền thông điệp và RPC

## Bài tập 1: Tìm hiểu RabbitMQ – Hệ thống truyền thông điệp

### 1. RabbitMQ là gì?
RabbitMQ là một hệ thống trung gian truyền thông điệp (Message Broker) mã nguồn mở, sử dụng giao thức AMQP (Advanced Message Queuing Protocol). Nó cho phép các hệ thống giao tiếp thông qua việc gửi và nhận thông điệp qua hàng đợi (queue).

### 2. Kiến trúc hoạt động
- **Producer**: Gửi thông điệp
- **Exchange**: Tiếp nhận và phân phối thông điệp đến các hàng đợi
- **Queue**: Lưu trữ thông điệp
- **Consumer**: Nhận và xử lý thông điệp

### 3. Các loại Exchange
- **Direct**: định tuyến theo tên chính xác
- **Topic**: định tuyến theo mẫu chuỗi (ví dụ: `log.*`)
- **Fanout**: phát broadcast tới tất cả queue
- **Headers**: định tuyến theo metadata

### 4. Cài đặt RabbitMQ
- **Dùng Docker**:
  ```bash
  docker run -d --hostname my-rabbit --name some-rabbit \
  -p 5672:5672 -p 15672:15672 rabbitmq:3-management

### Bài tập 2: Code hệ thống đơn giản sử dụng RabbitMQ
1. Mục tiêu
Tạo một hệ thống đơn giản có thể gửi và nhận thông điệp bằng RabbitMQ.

2. Cài đặt thư viện Python
```
bash

pip install pika
```
3. Producer – Gửi thông điệp
```
import pika
connection = pika.BlockingConnection(pika.ConnectionParameters('localhost'))
channel = connection.channel()
channel.queue_declare(queue='hello')

channel.basic_publish(exchange='', routing_key='hello', body='Hello RabbitMQ!')
print(" [x] Sent 'Hello RabbitMQ!'")
connection.close()
```

 4. Consumer – Nhận thông điệp
```
import pika

connection = pika.BlockingConnection(pika.ConnectionParameters('localhost'))
channel = connection.channel()
channel.queue_declare(queue='hello')

def callback(ch, method, properties, body):
    print(f" [x] Received {body}")

channel.basic_consume(queue='hello', on_message_callback=callback, auto_ack=True)

print(' [*] Waiting for messages. To exit press CTRL+C')
channel.start_consuming()
```
### Bài tập 3: Tìm hiểu RPC dùng định dạng JSON
1. RPC là gì?
RPC (Remote Procedure Call) là kỹ thuật gọi hàm từ xa, cho phép chương trình này gọi hàm do chương trình khác cung cấp như thể gọi hàm cục bộ.

2. JSON-RPC thay thế xmlrpc
Thay vì XML như xmlrpc.client, JSON-RPC sử dụng JSON để mã hóa dữ liệu, nhẹ hơn và dễ đọc.

3. Cài đặt Flask + JSON-RPC
```
bash
pip install flask flask-jsonrpc
```
4. Server: RPC sử dụng JSON
```
from flask import Flask
from flask_jsonrpc import JSONRPC

app = Flask(__name__)
jsonrpc = JSONRPC(app, '/api')

@jsonrpc.method('App.add')
def add(a: int, b: int) -> int:
    return a + b

if __name__ == '__main__':
    app.run()
```	
5. Client: Gửi yêu cầu gọi hàm từ xa
```
import requests

data = {
    "jsonrpc": "2.0",
    "method": "App.add",
    "params": [5, 3],
    "id": 1
}
response = requests.post("http://localhost:5000/api", json=data)
print(response.json())
```
