---
title : "Geolocation Routing"
date : "2025-08-07"
weight : 4
chapter : false
pre : " <b> 4. </b> "
---

#### Configure Geolocation Routing

1. Login to [AWS Console](https://aws.amazon.com/console/)

    - Search for **Route 53**
    - Select **Route 53**

2. In the **Route 53** dashboard

    - Select **Hosted zones** you've created
    - Choose **Create records**

![GeolocationRouting](/images/2/CWT1.png?featherlight=false&width=90pc)

![GeolocationRouting](/images/2/CWT2.png?featherlight=false&width=90pc)

{{% notice note %}}
Delete the other record types because Route 53 only allows one record with a matching Name/Type, then proceed to create the new record.
{{% /notice %}}

3. Create 2 A Records with a Routing Policy of Geolocation

- Record 1: Singapore

   - **Record name**: www
   - **Record type**: A
   - **Value**: Public IPv4 address of the EC2 in Singapore
   - **TTL** : 60
   - **Routing Policy**: Geolocation
   - **Location**: Asia
   - **Health check ID**: Choose Singapore Health check
   - **Record ID**: SG-Geolocation
   - Enter **Create records**

![GeolocationRouting](/images/2/CGC1.png?featherlight=false&width=90pc)

- Record 2: Virginia

   - **Record name**: www
   - **Record type**: A
   - **Value**: Public IPv4 address of the EC2 in Virginia
   - **TTL** : 300
   - **Routing Policy**: Geolocation
   - **Location**: North America
   - **Health check ID**: Choose Virginia Health check
   - **Record ID**: VG-Geolocation
   - Enter **Create records**

![GeolocationRouting](/images/2/CGC2.png?featherlight=false&width=90pc)

4. Test

- Use a testing tool from multiple locations, such as: https://geopeeker.com
- Access the domain address (e.g., http://www.workshopkhang.com)

![GeolocationRouting](/images/2/CGC3.png?featherlight=false&width=90pc)