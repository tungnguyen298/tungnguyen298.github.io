+++
title = "Transit Gateway Attachments"
date = 2020
weight = 3
chapter = false
pre = "<b>3. </b>"
+++
#### Tổng quan
Ở phần này, bạn sẽ cấu hình các **Transit Gateway Attachments** để gán các VPC vào Transit Gateway đã tạo.

![3_Infra](/images/transitgateway/3_Infra.png?width=40pc)

**Nội dung:**
- [Tạo Transit Gateway Attachments](#tạo-transit-gateway-attachments)

#### Tạo Transit Gateway Attachments
1. Mở **VPC Management Console**, chọn **Transit Gateway Attachments** ở thanh bên trái, và chọn **Create Transit Gateway Attachment**.

![3_CreateTGWA](/images/transitgateway/3_Create_TGW_Attachment.png?width=90pc)

2. Ở trang **Create Transit Gateway Attachment**, chọn các thông số sau và chọn **Create attachment**:
    - Transit Gateway ID: chọn ID của Transite Gateway được tạo.
    - Attachment type: chọn **VPC** để định dạng đối tượng được gán là VPC
    - Attachment name tag: nhập VPC tương úng với **VPC ID** (Ví dụ: VPC1)
    - VPC ID: chọn **First VPC**, tức VPC1.
    - Subnet ID: trong hạ tầng này, mỗi VPC chỉ chứa một subnet. Do đó, bạn chỉ có một lựa chọn là subnet ở một AZ nhất định.

![3_VPCAttachment](/images/transitgateway/3_VPC_TGWA.png?width=90pc)

3. Lặp lại **bước 1-2** với từng VPC và chúng ta sẽ có được kiến trúc như hình ở phần Tổng quan. Lưu ý mỗi VPC chỉ có 1 subnet nhưng ở môi trường production bạn thường sẽ gắn tất cả các subnet vào Transit Gateway.

4. Bây giờ, bạn hãy kết nối SSH đến các instance ở VPC1 và VPC3. Thử ping các địa chỉ IP private của các instance khác. Điều này sẽ không được bởi vì việc gán các VPC vào Transit Gateway không tự tạo các các trúc liên kết routing trong trường hợp này bởi vì cấu hình **Default route table association** và **Default route table propagation** đã bị vô hiệu hoá ở phần tạo Transit Gateway trước.  
![3_Test](/images/transitgateway/3_Test.png?width=90pc)

*Hình trên thể hiện ping thất bại từ **First EC2 Host** đến **Fourth EC2 Host**.