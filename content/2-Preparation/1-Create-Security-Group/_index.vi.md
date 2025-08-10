---
title : "Tạo Security Group"
date : "2025-08-07"
weight : 1
chapter: false
pre : " <b> 2.1 </b> "
---

{{% notice note %}}
Chúng ta cần tạo **2 Security group** ở 2 **region** khác nhau, chọn 2 region là Singapore và N.Virginia
{{% /notice %}}

#### Cấu hình Security Group 

Security Group hoạt động như tường lửa ảo để kiểm soát lưu lượng truy cập vào và ra khỏi EC2 instance. Trong phần này, chúng ta sẽ tạo Security Group với các quy tắc phù hợp cho EC2 instance.

Dưới đây là các bước tạo Security group thuộc region **Singapore**:

1. Đăng nhập vào [AWS Console](https://aws.amazon.com/console/).

    - Tìm và chọn **EC2**
    - Chọn **Security Group**

![CreateSG](/images/1/CreateSG.png?featherlight=false&width=90pc)

2. Trong giao diện **Create security group**

    - **Security group name**: nhập `web-sg`
    - **Description**: nhập `Allows SSH and HTTP access`
    - **VPC**: Giữ nguyên VPC mặc định (default)

![CreateSG](/images/1/CSG1.png?featherlight=false&width=90pc)

3. Cấu hình **Inbound rules**: ta cần them 3 inbound rules bằng cách click **Add rule** rồi lần lượt cấu hình như sau:

| Type  | Protocol | Port range |    Soucre     |
| ----- | -------- | ---------- | ------------- |
| SSH   |   TCP    |     22     |     My IP     |
| HTTP  |   TCP    |     80     | AnyWhere-IPv4 |
| HTTPS |   TCP    |     443    | AnyWhere-IPv4 |

![CreateSG](/images/1/CSG2.png?featherlight=false&width=90pc)

4. Nhấn **Create security group**

![CreateSG](/images/1/CSG3.png?featherlight=false&width=90pc)

![CreateSG](/images/1/CSG4.png?featherlight=false&width=90pc)

{{% notice note %}}
Tương tự với các bước tạo Security group ở region N.Virginia (đặt tên security group name là web-vg)
{{% /notice %}}

![CreateSG](/images/1/CSG5.png?featherlight=false&width=90pc)
