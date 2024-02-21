---
title : "Kết nối Bastion Host"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 2.3. </b> "
---

1. Đi đến [EC2 instances](https://us-west-2.console.aws.amazon.com/ec2/home?region=us-west-2#Instances:instanceState=running).
2. Chọn máy chủ tên là **MID-Bastion**.
3. Nhấn **Connect**.
![Connect Bastion Host](/images/2.prerequires/2.3connectbastion/2.3.1connectbastion.png?width=90pc)

4. Tại trang **Connect to instance**, chọn **RDP client**.
5. Nhấn **Download remote desktop file**.
6. Nhấn **Get password**.
![Connect Bastion Host](/images/2.prerequires/2.3connectbastion/2.3.2connectbastion.png?width=90pc)

 {{%notice warning%}}
Đảm bảo rằng tệp tên **MID-Bastion.rdp** đã được tải xuống thành công.
{{%/notice%}}

7. Tại trang **Get Windows password**, nhấn **Upload private key file**.
8. Sau đó, nhấn **Decrypt password**.
![Connect Bastion Host](/images/2.prerequires/2.3connectbastion/2.3.3connectbastion.png?width=90pc)

9. Mật khẩu đã được tạo ra.
![Connect Bastion Host](/images/2.prerequires/2.3connectbastion/2.3.4connectbastion.png?width=90pc)

10. Mở tệp **MID-Bastion.rdp** với mật khẩu trên.

Chúc mừng!Bạn đã kết nối tới máy chủ Bastion Host thành công.
