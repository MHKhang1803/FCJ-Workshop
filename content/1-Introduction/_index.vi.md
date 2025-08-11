---
title : "Giới thiệu"
date : "2025-08-07"
weight : 1
chapter : false
pre : " <b> 1. </b> "
---

#### Tổng quan
**Global Load Balancing với Route 53 và Health Checks** nhằm mục tiêu xây dựng một giải pháp cân bằng tải toàn cầu dựa trên dịch vụ DNS của AWS – Amazon Route 53. Bằng cách sử dụng các tính năng như **Weighted Routing**, **Geolocation Routing**, và **Failover Routing** kết hợp với **Health Checks**, hệ thống có thể tự động điều hướng người dùng đến máy chủ phù hợp nhất dựa trên vị trí địa lý, tình trạng hoạt động hoặc chính sách tải định sẵn. Điều này giúp tăng cường tính sẵn sàng, hiệu suất truy cập và khả năng phục hồi của ứng dụng trên phạm vi toàn cầu.

#### Route 53
**Amazon Route 53** là dịch vụ DNS (Domain Name System) được quản lý bởi AWS, cung cấp khả năng phân giải tên miền một cách nhanh chóng, đáng tin cậy và linh hoạt. Route 53 cho phép người dùng định tuyến lưu lượng truy cập đến các máy chủ, ứng dụng hoặc tài nguyên AWS dựa trên nhiều chính sách như địa lý, trọng số và trạng thái sức khỏe của endpoint. Ngoài ra, dịch vụ còn hỗ trợ mua và quản lý tên miền, giúp doanh nghiệp xây dựng hạ tầng mạng toàn cầu với hiệu suất cao và độ sẵn sàng tối ưu.

#### EC2
**Amazon EC2 (Elastic Compute Cloud)** là dịch vụ điện toán đám mây của AWS cho phép người dùng khởi tạo và quản lý các máy chủ ảo (instance) một cách linh hoạt và theo nhu cầu. Với EC2, người dùng có thể dễ dàng triển khai ứng dụng, lưu trữ dữ liệu, cấu hình hệ điều hành, và mở rộng hạ tầng khi cần thiết. Dịch vụ này hỗ trợ nhiều loại instance phù hợp với các mục đích khác nhau như web server, xử lý dữ liệu, hay machine learning, giúp tiết kiệm chi phí và tối ưu hiệu suất vận hành.

![Introduction](/FCJ-Workshop/images/1/AWSWorkshop.png?featherlight=false&width=90pc)