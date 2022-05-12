+++
title = "Thiết lập Hạ tầng"
date = 2020
weight = 1
chapter = false
pre = "<b>1. </b>"
+++
#### Tổng quan
Ở phần này, bạn sẽ thiết lập hạ tầng mạng với CloudFormation Template cho bài lab với kiến trúc sau:

![1_Infra](/images/transitgateway/1_Infra.png?width=40pc)
Như vậy, tài nguyên được triển khai bao gồm:
- **First EC2 Host** ở VPC1 và **Third EC2 Host** ở VPC3 có thể được kết nối thông qua Internet
- **Second EC2 Host** ở VPC2 và **Fourth EC2 Host** ở VPC4 không thể được kết nối thông qua Internet

#### Thiết lập Hạ tầng
1. Tải Template tên **tgw-lab.yaml** trong link [**này**](https://github.com/aws-samples/aws-transit-gateway-routing-lab) hoặc tải file dưới đây:

{{%attachments title="tgw-lab" pattern="tgw-lab" style="orange"/%}}

2. Truy cập đến **CloudFormation Management Conole** bằng cách gõ **CloudFormation** vào thanh tìm kiếm.

![1_CloudFormation](/images/transitgateway/Create_CloudFormation.png?width=40pc)

3. Ở thanh bên trái, chọn **Stacks**. Sau đó, nhấn chọn **Create Stack** và **With new resources (standard)**.

![1_CreateStack](/images/transitgateway/Create_Stack.png?width=90pc)

4. Chọn **Upload a template file**, chọn **tgw-lab.yaml** từ source mà chúng ta down về ở trên, và chọn **Next**.

![1_YAML](/images/transitgateway/Upload_Yaml.png?width=90pc)

5. Trong trang **Specify stack details**, nhập tên cho stack (VD: Lab-Stack), chọn SSH Key của bạn, và sau đó chọn **Next**:

![1_SpecifyDetails](/images/transitgateway/Specify_Stack_Details.png?width=90pc)

6. Trong trang **Configure stack options**, giữ nguyên mặc định và chọn **Next**.

![1_StackOptions](/images/transitgateway/Configure_Stack_Options.png?width=90pc)

7. Trong trang **Review**, kiểm tra thông tin và chọn **Create stack**.

8. Sau khi CloudFormation tạo hoàn thành. Đi đến folder bạn chứa SSH Key pair và sau đó chạy command sau để sao chép Key Pair đến **First EC2 Host** và **Third EC2 Host** cho bước tiếp theo.
    ```
    scp -i <key name> <key name> ec2-user@<public ip>:
    ```
![1_CopyKey](/images/transitgateway/Copied_Key.png?width=90pc)

{{% notice note %}}
Lệnh **scp** sẽ có sẵn ở trên hệ điều hành Linux và Mac. Nếu bạn sử dụng hệ điều hành Windows, hãy cài đặt **PuTTY** để có thể sử dụng lệnh và kết nối tới EC2 instance.


