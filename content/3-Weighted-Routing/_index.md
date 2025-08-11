---
title : "Weighted Routing"
date : "2025-08-07"
weight : 3
chapter : false
pre : " <b> 3. </b> "
---

#### Configure Weighted Routing

1. Login to [AWS Console](https://aws.amazon.com/console/)

    - Search for **Route 53**
    - Select **Route 53**

2. In the **Route 53** dashboard

    - Select **Hosted zones** you've created
    - Choose **Create records**

![WeightedRouting](/FCJ-Workshop/images/2/CWT1.png?featherlight=false&width=90pc)

![WeightedRouting](/FCJ-Workshop/images/2/CWT2.png?featherlight=false&width=90pc)

1. Create 2 A Records with a Routing Policy of Weighted

- Record 1: Singapore

   - **Record name**: www
   - **Record type**: A
   - **Value**: Public IPv4 address of the EC2 in Singapore
   - **TTL** : 300
   - **Routing Policy**: Weighted
   - **Weight**: 50
   - **Health check ID**: Choose Singapore Health check
   - **Record ID**: SG-Weighted
   - Enter **Create records**

![WeightedRouting](/FCJ-Workshop/images/2/CWT3.png?featherlight=false&width=90pc)

- Record 2: Virginia

   - **Record name**: www
   - **Record type**: A
   - **Value**: Public IPv4 address of the EC2 in Virginia
   - **TTL** : 300
   - **Routing Policy**: Weighted
   - **Weight**: 50
   - **Health check ID**: Choose Virginia Health check
   - **Record ID**: VG-Weighted
   - Enter **Create records**

![WeightedRouting](/FCJ-Workshop/images/2/CWT4.png?featherlight=false&width=90pc)

4. Test

- Open a browser and navigate to your domain (e.g., http://www.workshopkhang.com).
- Refresh the page multiple times, and you should see:

   - Sometimes the content "Web Server in Singapore".
   - Sometimes the content "Web Server in Virginia".
   - The frequency should reflect the 50/50 ratio you configured

![WeightedRouting](/FCJ-Workshop/images/2/CWT5.png?featherlight=false&width=90pc)

![WeightedRouting](/FCJ-Workshop/images/2/CWT6.png?featherlight=false&width=90pc)
