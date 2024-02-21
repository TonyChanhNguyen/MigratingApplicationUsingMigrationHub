---
title : "Cấu hình target template mặc định"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 4.1.2 </b> "
---
AWS MGN cho phép thiết lập các mẫu mặc định cho cấu hình phiên bản đích, bao gồm cài đặt Launch Templates và Post-Launch. Những mẫu này sẽ được áp dụng cho mỗi máy chủ mới được thêm vào danh sách máy chủ nguồn AWS MGN, việc này xảy ra sau khi AWS Replication Agent được cài đặt trên máy chủ nguồn.
### Xác định cấu hình phiên bản mục tiêu mặc định
AWS MGN sử dụng một **EC2 Launch Template** để xác định cấu hình của các phiên bản EC2 mục tiêu trong gian đoạn thử nghiệm và dịch chuyển chuyển tiếp.
1. Bên dưới **Settings**, chọn **Launch template**.
2. Nhấn **Edit**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.2defaulttemplate/4.1.2.1defaulttemplate.png?width=90pc)

3. Tại tính năng **General launch settings**, bỏ chọn **Activate instance type right-sizing**.
4. Kiêm tra **Transfer server tags**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.2defaulttemplate/4.1.2.2defaulttemplate.png?width=90pc)

5. Tại tính năng **Default EC2 Launch Template**, chọn lớp mạng **TargetPublic** tại **Default target subnet**
6. Chọn nhóm bảo mật tên **FCJ-MigrationHub-Workshop-SOURCENETWORK-XXXXXXXXXXXX-TargetSecurityGroup-XXXXXXXXXXXX** tại **Additional security groups**.
7. Chọn **t3.small** tại **Default instance type**
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.2defaulttemplate/4.1.2.3defaulttemplate.png?width=90pc)

8. Sau đó, nhấn **Save template**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.2defaulttemplate/4.1.2.4defaulttemplate.png?width=90pc)

9. Chờ vài phút và đảm bảo thay đổi của bạn đã được lưu.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.2defaulttemplate/4.1.2.5defaulttemplate.png?width=90pc)


### Xác định tích hợp sau khi ra mắt các phiên bản mục tiêu mặc định
AWS MGN sử dụng cấu hình **Post-Launch Template** để xác định mọi hành động tự động hóa sau khi khởi chạy sẽ được thực thi trên các máy chủ EC2 mục tiêu sau khi khởi chạy thành công máy chủ thử nghiệm / chuyển đổi. Trong bước này chúng ta sẽ sử mẫu AWS MGN Post-Launch mặc định để cấu hình tích hợp với **AWS Systems Manager** với các máy chủ được dịch chuyển. Điều này sẽ tự động kích hoạt tính năng **AWS System Manager** như là Fleet Management, Inventory, Patch Management, thực thi Remote, thực thi của Automation documents. 
1. Bên dưới **Settings**, chọn **Post-launch template**.
2. Nhấn **Edit**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.2defaulttemplate/4.1.2.6defaulttemplate.png?width=90pc)

3. Chọn *Install the Systems Manager agent and allow executing actions on launched servers*.
4. Giữ lựa chọn **Deployment** tại **Test and Cutover instances**.
5. Sau đó, nhấn **Save template**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.2defaulttemplate/4.1.2.7defaulttemplate.png?width=90pc)

6. Sau khi chúng ta cấu hình **Post-Launch template** để kích hoạt tích hợp **AWS System Manager Agent (SSM Agent)**, Các tài liệu tự động hóa SSM khác có thể được kích hoạt khi khởi chạy thành công các phiên bản kiểm thử hoặc chuyển đổi.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.2defaulttemplate/4.1.2.8defaulttemplate.png?width=90pc)
