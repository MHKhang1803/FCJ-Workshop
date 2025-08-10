---
title: "Các bước chuẩn bị"
date: "2025-08-07"
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

#### Tổng quan

Bước đầu tiên chúng ta sẽ tạo **2 Security Group** để kết nối với **2 EC2 instance** ở **2 region** khác nhau, tạo **2 Health Check**, tạo **Hosted Zone**

{{% notice note %}}
Cần phải có 1 Domain Route 53.
{{% /notice %}}

#### Nội dung

1. [Tạo Security Group]({{< relref "1-Create-Security-Group" >}})
2. [Tạo EC2 Instance]({{< relref "2-Create-EC2-Instance" >}})
3. [Tạo Health Check]({{< relref "3-Create-Health-Check" >}})
4. [Tạo Hosted Zone]({{< relref "4-Create-Hosted-Zone" >}})
