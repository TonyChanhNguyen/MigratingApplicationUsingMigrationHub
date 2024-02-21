---
title : "Triển khai máy chủ chuyển đổi"
date :  "`r Sys.Date()`" 
weight : 8
chapter : false
pre : " <b> 4.1.8 </b> "
---
1. Khi các máy chủ ở trạng thái **Ready for cutover**, chọn tất cả 2 máy chủ để bắt đầu chuyển đổi. 
2. Chọn **Test and Cutover** trên cùng bên phải.
3. Sau đó dưới mục **Cutover**, chọn **Launch cutover instances**.
![Migrating your application](../../../../images/4.migrateinfra/4.1migrateapp/4.1.8cutover/4.1.8.1cutover.png?width=90pc)

4. Nhấn **Launch**.
![Migrating your application](../../../../images/4.migrateinfra/4.1migrateapp/4.1.8cutover/4.1.8.2cutover.png?width=90pc)

5. Trạng thái của **Migration lifecycle** thay đổi thành **Cutover in progress**.
6. Thông tin chi tiết, nhấn **View job details**.
![Migrating your application](../../../../images/4.migrateinfra/4.1migrateapp/4.1.8cutover/4.1.8.3cutover.png?width=90pc)

7. Chờ 10-15 phút, **Status** của **Source server name** sẽ thành **Launched**.
![Migrating your application](../../../../images/4.migrateinfra/4.1migrateapp/4.1.8cutover/4.1.8.4cutover.png?width=90pc)
Hiện tại khi tất cả các máy chủ được khởi tạo phiên bản chuyển đổi mới, chúng ta cần xác nhận ứng dụng trong môi trường mới.
