---
title : "Tạo Key Pair"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 2.1 </b> "
---

Trong bước này, chúng ta sẽ tạo một public key pair để cung cấp cho mẫu CloudFormation khi triển khai Bastion Host. Private key pair sẽ được sử dụng để giải mã mật khẩu của Bastion Host thực hiện kết nối tới Bastion Host sử dụng SSM Fleet Manager hoặc RDP client. 
1. Đi đến [Key Pair](https://us-west-2.console.aws.amazon.com/ec2/home?region=us-west-2#KeyPairs:) of region ***Oregon (us-west-2)***
2. Nhấn **Create Key Pair**.
![Create Key Pair](../../../images/2.prerequires/2.1createkeypair/2.1.1createkeypair.png?width=90pc)

3. Tại mục **Name**, nhập vào ```FCJ-keypair```.
4. Tại **Key pair type**, chọn **RSA**.
5. Tại **Private key file format**, chọn **.pem**.
6. Sau đó nhấn **Create key pair**.
![Create Key Pair](../../../images/2.prerequires/2.1createkeypair/2.1.2.1createkeypair.png?width=90pc)

7. Kiểm tra key pair của bạn đã được tạo thành công.
![Create Key Pair](../../../images/2.prerequires/2.1createkeypair/2.1.3createkeypair.png?width=90pc)

 {{%notice warning%}}
Đảm bảo ràng tệp key pair của bạn đã được tải xuống tự động.
{{%/notice%}}

8. Mở **PuttyGen**. Nếu bạn vẫn chưa tải **PuttyGen**, tham khảo [here](https://www.puttygen.com/) để có thêm thông tin.
9. Nhấn **File**, sau đó nhấn **Load Private Key**.
10. Chọn tệp **FCJ-keypair.pem** mà bạn vừa tải xuống.

 {{%notice tip%}}
Chọn **All file** để thấy **FCJ-keypair.pem**.
{{%/notice%}}

11. Để trống tại **Key comment**.
12. Sao chép public key.
![Create Key Pair](../../../images/2.prerequires/2.1createkeypair/2.1.6createkeypair.png?width=30pc)
13. Lưu lại để sử dụng sau.


