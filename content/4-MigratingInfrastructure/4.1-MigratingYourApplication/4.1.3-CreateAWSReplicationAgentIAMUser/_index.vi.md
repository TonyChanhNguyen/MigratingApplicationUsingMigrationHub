---
title : "Tạo IAM user cho AWS replication agent"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 4.1.3 </b> "
---
**The AWS Replication Agent (MGN agent)** sẽ được cài đặt bên trong máy chủ nguồn yêu cầu các quyền IAM để đăng ký máy nguồn với AWS MGN. Trong bước này chúng ta sẽ tạo người dùng IAM được yêu cầu sẽ được sử dụng bởi AWS Replication Agent trong các bước tiếp theo.

1. Đi đến [IAM](https://us-east-1.console.aws.amazon.com/iam/home?region=us-west-2#/home). Chọn tính năng **User**.
2. Nhấn **Create user**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.3createiamuser/4.1.3.1createiamuser.png?width=90pc)

3. Nhập tên người dùng ```MGNuser```.
4. Nhấn **Next**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.3createiamuser/4.1.3.2createiamuser.png?width=90pc)

5. Tại **Permissions options**, chọn **Attach policies directly**.
6. Tại **Permissions policies**, tìm kiếm và chọn chính sách tên **AWSApplicationMigrationAgentInstallationPolicy**.
7. Sau đó, nhấn **Next**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.3createiamuser/4.1.3.3createiamuser.png?width=90pc)

8. Kiểm tra lại và nhấn **Create user**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.3createiamuser/4.1.3.4createiamuser.png?width=90pc)

9. Nhấn **View user**, chọn tab **Security credentials**.
10. Nhấn **Create credential**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.3createiamuser/4.1.3.5createiamuser.png?width=90pc)

11. Chọn **Application running outside AWS**.
12. Sau đó, nhấn **Next**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.3createiamuser/4.1.3.6createiamuser.png?width=90pc)

13. Kế tiếp, nhấn **Create access key**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.3createiamuser/4.1.3.7createiamuser.png?width=90pc)

14. Tải xuống tệp chứng thực bằng cách nhấn **Download .csv file**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.3createiamuser/4.1.3.8createiamuser.png?width=90pc)
