+++
title = "Create Route Table for TGW"
date = 2020
weight = 4
chapter = false
pre = "<b>4. </b>"
+++
#### Overview

In this section, You will create Transit Gateway Route Table so that Transit Gateway knows which **VPC attachment** are available to send and receive traffic deliverd through TRansit Gateway

**Content:**
- [Tạo Transit Gateway Route Tables](#tạo-transit-gateway-route-tables)

#### Create Transit Gateway Route Table
1. Open **VPC Management Console**, Choose **Transit Gateway Route Tables** at left side bar, then choose **Create Transit Gateway Route Table**.

![3_CreateTGWRT](/images/transitgateway/3_Create_TGW_RT.png?width=90pc)

2. Enter **Name tag** (VD:lab-TGW-RT), Select Transit Gateway which you created, then choose **Create Transit Gateway Route Table**.

![3_ConfigureTGWRT](/images/transitgateway/3_Config_TGW_RT.png?width=90pc)

3. After Route Table are available, tick to route table which you created, choosetab **Associations**, then click **Create association**.

![4_CreateAssociation](/images/transitgateway/4_Create_TGW_Associations.png?width=90pc)

5. Lần lượt đính từng VPC. Quá trình association báo Transit Gateway biết route table của VPC nào sẽ gửi các data packet tới Transit Gateway.

![4_Config Associations](/images/transitgateway/4_Config_TGW_Associations.png?width=90pc)

![4_AllAss](/images/transitgateway/4_Attached_VPC.png?width=90pc)

6. Move to tab **Propagations**, click to **Create propagation**. 
s
![4_CreatePropagation](/images/transitgateway/4_Create_Propagations.png?width=90pc)

7. Lần lượt đính từng VPC. Quá trình propagation báo Transit Gateway biết route table của VPC nào sẽ nhận các data packet từ Transit Gateway.

![4_CreatePropagation](/images/transitgateway/4_Config_TGW_Propagations.png?width=90pc)

![4_AllPro](/images/transitgateway/4_Attached_VPC_Propagations.png?width=90pc)

