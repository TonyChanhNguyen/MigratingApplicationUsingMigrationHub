---
title : "Tải AWS Replication Agent"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 4.1.4 </b> "
---
AWS Application Migration Service nhân bản dữ liệu sáng AWS bẳng các agent mà đã được cài đặt bên trong máy chủ nguồn.
1. Đi đến [Source server](https://us-west-2.console.aws.amazon.com/mgn/home?region=us-west-2#/sourceServers) của Application Migration Service.
2. Nhấn **Add server**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.4installagent/4.1.4.1installagent.png?width=90pc)

3. Tại **Select your operating system**, chọn **Linux**.
4. Tại **IAM access key ID**, nhập **IAM access key ID** của **MGNuser**.
5. Tại **IAM secret access key**, nhâp **IAM secret access key** của **MGNuser**.
6. Sao chép dòng lệnh của mục 5 và 6.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.4installagent/4.1.4.2installagent.png?width=90pc)

Bây giờ bạn sẽ đi đến Bastion Host để cài đặt agent cho các máy chủ.
7. Đăng nhập vào Bastion Host
8. Sử dụng Putty trong Bastion Host để SSH tới các máy chủ.
9. SSH đến Offbiz-web và Offbiz-db.
+ Đăng nhập: user
+ Mật khẩu: 12345678
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.4installagent/4.1.4.3installagent.png?width=90pc)

10. Chạy các dòng lệnh đã sao chép ở bước 6.
11. Cài đặt agent trên mỗi máy chủ sẽ mất khoảng 3-5 phút. Khi agent được cài đặt, bạn sẽ thấy AWS Replication Agent tin nhắn cài đặt thành công trên giao diện SSH.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.4installagent/4.1.4.4installagent.png?width=90pc)

Bạn cũng sẽ thấy các máy chủ được thêm vào **AWS Application Service** bên dưới danh sách **Source Servers** ở giai đoạn khởi tạo.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.4installagent/4.1.4.5installagent.png?width=90pc)