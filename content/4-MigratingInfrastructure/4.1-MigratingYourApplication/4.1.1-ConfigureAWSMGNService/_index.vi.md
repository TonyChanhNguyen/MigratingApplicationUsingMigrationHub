---
title : "Cấu hình dịch vụ AWS MGN"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 4.1.1 </b> "
---

Application Migration Service phải được khởi tạo khi sử dụng lần đầu trong mỗi tài khoản AWS và Region nơi việc sao chép sẽ cần diễn ra. Bước đầu tiên là tạo mẫu Replication Settings, sau đó dịch vụ được khởi tạo bằng cách tạo IAM Roles cần thiết để dịch vụ hoạt động.

1. Đi đến [AWS Application Migration Service](https://us-west-2.console.aws.amazon.com/mgn/home?region=us-west-2#) .
2. Nhấn **Get started**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.1configure/4.1.1.1configure.png?width=90pc)

3. Chọn **Set up service**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.1configure/4.1.1.2configure.png?width=90pc)

4. Khi **Application Migration Service** được khởi tạo, bạn sẽ được chuyển hướng đến trang **Application Migration Service Console Source Servers**.
5. Bên dưới **Settings**, chọn **Replication template**.
6. Sau đó, nhấn **Edit**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.1configure/4.1.1.3configure.png?width=90pc)

7. Tại **Staging area subnet**, chọn lớp mạng con **Target Public**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.1configure/4.1.1.4configure.png?width=90pc)

8. Thêm nhãn **Environment** và giá trị là **Migration-Staging**.
9. Sau đó, nhấn **Save template**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.1configure/4.1.1.5configure.png?width=90pc)

10. Wait a second and make sure your changes are saved.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.1configure/4.1.1.6configure.png?width=90pc)




