+++
title = "Dọn dẹp tài nguyên"
date = 2021-07-08T10:41:06+07:00
weight = 6
chapter = false
pre = "<b>6. </b>"
+++

Bạn sẽ dọn dẹp tài nguyên theo thứ tự sau:
1. **Xóa TGW Attachments**
    - Truy cập vào **VPC Management Console**
    - Ở thanh bên trái, chọn Transit Gateway Attachments.
    - Lần lượt tick vào các Attachment liên quan tới bài, chọn Actions, và chọn Delete
    - Trong prompt, chọn Delete.
    - Đọi 1-2 để hoàn thành việc xóa các attachment
2. **Xóa Transit Gateway**
    - Truy cập vào **VPC Management Console**
    - Ở thanh bên trái, chọn Transit Gateways.
    - Tick vào các Attachment liên quan tới bài, chọn Actions, và chọn Delete
    - Trong prompt, chọn Delete. Bạn phải đợi TGW Attachments được xóa hoàn toàn trước khi xóa TGW.
    - Đọi 1-2 để hoàn thành việc xóa TGW.
3. **Xóa CloudFormation Stack**
    - Truy cập vào **CloudFormation Management Console**
    - Ở thanh bên trái, chọn Stacks.
    - Tick vào CloudFormation Stack liên quan tới bài lab và chọn Delete.
    - Trong prompt, chọn Delete stack.
    - Đọi vài phút cho tới khi CloudFormation xóa bỏ hết tài nguyên.
