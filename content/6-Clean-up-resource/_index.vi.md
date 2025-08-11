---
title : "Dọn dẹp tài nguyên"
date : "2025-08-07"
weight : 6
chapter : false
pre : " <b> 6. </b> "
---

#### Xóa Health Check

- Vào **Route 53** → **Health checks**
- Chọn các health check đã tạo → Delete

![Cleanup](/static/images/02/CR1.png?featherlight=false&width=90pc)

#### Xóa bản ghi DNS trong Hosted Zone

- Vào **Route 53** → **Hosted zones**
- Mở domain 
- Chọn và xóa các bản ghi Weighted/Failover/Geolocation đã tạo

![Cleanup](/static/images/02/CR2.png?featherlight=false&width=90pc)

#### Xóa Hosted Zone

- Chỉ xóa khi bạn không còn nhu cầu sử dụng domain/zone

![Cleanup](/static/images/02/CR3.png?featherlight=false&width=90pc)

#### Terminate EC2 instance

{{% notice note %}}
Dọn dẹp trên cả 2 region Singapore và Virginia 
{{% /notice %}}

1. Truy cập vào **EC2** console
2. Chọn **Instances**
3. Chọn các instance liên quan đến workshop
4. Chọn **Instance state**
5. Chọn **Terminate instance**

![Cleanup](/static/images/02/CR4.png?featherlight=false&width=90pc)

![Cleanup](/static/images/02/CR5.png?featherlight=false&width=90pc)

#### Xóa Security group

{{% notice note %}}
Dọn dẹp trên cả 2 region Singapore và Virginia 
{{% /notice %}}

1. Truy cập vào **EC2** console
2. Chọn **Security Groups** trong mục Network & Security
3. Chọn security group liên quan đến workshop
4. Chọn **Actions**
5. Chọn **Delete security groups**

![Cleanup](/static/images/02/CR6.png?featherlight=false&width=90pc)

#### Xóa Key Pair

{{% notice note %}}
Dọn dẹp trên cả 2 region Singapore và Virginia 
{{% /notice %}}

1. Truy cập **EC2** console
2. Chọn **Key Pairs** trong mục Network & Security
3. Chọn key pair liên quan đến workshop
4. Chọn **Actions**
5. Chọn **Delete**

![Cleanup](/static/images/02/CR7.png?featherlight=false&width=90pc)
