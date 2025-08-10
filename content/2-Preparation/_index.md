---
title: "Preparation"
date: "2025-08-07"
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

#### Overview

The first step is to create **2 Security Groups** to connect to **2 EC2 instances** in **2 different regions**. We will then create **2 Health Checks** and **a Hosted Zone**.

{{% notice note %}}
A Route 53 Domain is required.
{{% /notice %}}

#### Workshop Modules

1. [Create Security Group]({{< relref "1-Create-Security-Group" >}})
2. [Create EC2 Instance]({{< relref "2-Create-EC2-Instance" >}})
3. [Create Health Check]({{< relref "3-Create-Health-Check" >}})
4. [Create Hosted Zone]({{< relref "4-Create-Hosted-Zone" >}})