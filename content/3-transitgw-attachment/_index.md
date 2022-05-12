+++
title = "Transit Gateway Attachments"
date = 2020
weight = 3
chapter = false
pre = "<b>3. </b>"
+++
#### Overview
In this part, You will configure **Transit Gateway Attachments** to assign VPC to Transit Gateway .

![3_Infra](/images/transitgateway/3_Infra.png?width=40pc)

**Content:**
- [Tạo Transit Gateway Attachments](#tạo-transit-gateway-attachments)

#### Create Transit Gateway Attachments
1. Open **VPC Management Console**, choose **Transit Gateway Attachments** at left side bar, then choose **Create Transit Gateway Attachment**.

![3_CreateTGWA](/images/transitgateway/3_Create_TGW_Attachment.png?width=90pc)

2. At page: **Create Transit Gateway Attachment**, select belown information then choose **Create attachment**:
    - Transit Gateway ID: select generated Transit Gateway ID.
    - Attachment type: choose **VPC** to assgin object as VPC
    - Attachment name tag: enter the corresponding VPC with **VPC ID** (EX: VPC1)
    - VPC ID: choose **First VPC**, VPC1.
    - Subnet ID: In this infrastructure, each VPC contains only one subnet. Therefore, you only have one choice, it is specific AZ's subnet.

![3_VPCAttachment](/images/transitgateway/3_VPC_TGWA.png?width=90pc)

3. Repeat **Step 1-2** with each VPC then we will get architecture as showed in Overview. Note: In this lab each VPC only have 1 subnet but in production environment you will attach all subnet to Transit Gateway.

4. Now, you need to SSH to instances in VPC1 and VPC3. Try pinging the private IP addresses of other instances. This should not work because assigning VPCs to Transit Gateway does not create routing topologies in this case **Default route table association** and **Default route table propagation** were disabled in the previous Transit Gateway creation.

![3_Test](/images/transitgateway/3_Test.png?width=90pc)

*The image above showed ping failed from **First EC2 Host** to **Fourth EC2 Host**.