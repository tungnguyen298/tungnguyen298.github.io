+++
title = "Create Transit Gateway"
date = 2020
weight = 2
chapter = false
pre = "<b>2. </b>"
+++
#### Over view
In this part, you will create **Transit Gateway** on AWS Cloud. 

![2_Infra](/images/transitgateway/2_Infra.png?width=40pc)


**Content:**
- [ Transit Gateway](#tạo-transit-gateway)

#### Tạo Transit Gateway
1. Open **VPC Management Console**, Choose **Transit Gateway** at left side bar, then choose **Create Transit Gateway**.

![2_CreateTGW](/images/transitgateway/2_Create_TGW.png?width=90pc)

2. At **Create Transit Gateway** page, fill up information as below
    - Name tag: **lab-tgw**
    - Description: **Transit Gateway**
    - Configure the Transit Gateway: Uncheck **Default route table association** and **Default route table propagation**.
{{% notice note %}}
We will configure manually for **Default route table association** and **Default route table propagation** to understand how Route Table work
{{% /notice %}}

3. Choose **Create Transit Gateway**.

![2_ConfigureTGW](/images/transitgateway/2_Config_TGW.png?width=90pc)

4. We will wait 1 - 2 minutes for **Transit Gateway** become available

