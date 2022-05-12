+++
title = "Setting up Infrastructure"
date = 2020
weight = 1
chapter = false
pre = "<b>1. </b>"
+++
#### Tổng quan
In this part, you will set up the network infrastructure with CloudFormation Template for the lab with the following architecture:

![1_Infra](/images/transitgateway/1_Infra.png?width=40pc)
Below is resource you need to deploy for your lab:
- **First EC2 Host** at VPC1 and **Third EC2 Host** at VPC3 can connect via Internet
- **Second EC2 Host** at VPC2 and **Fourth EC2 Host** at VPC 4 cannot connect via Internet

#### Thiết lập Hạ tầng
1. Upload template **tgw-lab.yaml** t link [**this link**](https://github.com/aws-samples/aws-transit-gateway-routing-lab) or download below file:

{{%attachments title="tgw-lab" pattern="tgw-lab" style="orange"/%}}

2. Access to **CloudFormation Management Conole** by typing **CloudFormation** to address bar.

![1_CloudFormation](/images/transitgateway/Create_CloudFormation.png?width=40pc)

3. At left navigation, Choose **Stacks**. then choose **Create Stack** and **With new resources (standard)**.

![1_CreateStack](/images/transitgateway/Create_Stack.png?width=90pc)

4. Choose **Upload a template file**, choose **tgw-lab.yaml** from source download at step 1 , choose **Next**.

![1_YAML](/images/transitgateway/Upload_Yaml.png?width=90pc)

5. At **Specify stack details**, type Stack name (EX: Lab-Stack), choose your SSH key, then choose **Next**:

![1_SpecifyDetails](/images/transitgateway/Specify_Stack_Details.png?width=90pc)

6. At **Configure stack options**, keep default then choose **Next**.

![1_StackOptions](/images/transitgateway/Configure_Stack_Options.png?width=90pc)

7. At **Review**, check infomration then choose **Create stack**.

8. After CloudFormation creatted, Go to folder stored SSH Key pair and run below command to copy key pair to **First EC2 Host** and **Third EC2 Host** to prepare for next step.
    ```
    scp -i <key name> <key name> ec2-user@<public ip>:
    ```
![1_CopyKey](/images/transitgateway/Copied_Key.png?width=90pc)

{{% notice note %}}
Command **scp** already available in Linux and Mac OS. If you are using Windows OS, you need to install **PuTTY** to use command and connect to EC2 instances


