---
title : "Triển khai máy chủ kiểm thử"
date :  "`r Sys.Date()`" 
weight : 6
chapter : false
pre : " <b> 4.1.6 </b> "
---
1. Khi trạng thái của máy chủ chuyển thành **Ready for testing** trên thanh điều hướng **AWS Application Migration Service**. Bạn có thể thực hiện kiểm thử cho máy chủ đó.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.6testing/4.1.6.1testing.png?width=90pc)

2. Chọn máy chủ để khởi chạy ở chế độ thử nghiệm.
3. Nhấn **Test and Cutover**.
4. Sau đó, chọn **Launch Test Instance**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.6testing/4.1.6.2testing.png?width=90pc)

5. Nhấn **Launch**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.6testing/4.1.6.3testing.png?width=90pc)

6. Điều này sẽ thay đổi **Migration Lifecycle Status** thành **Test in progress**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.6testing/4.1.6.4testing.png?width=90pc)

7. Nhấn **ofbiz-db.onpremsim.env** và thấy việc kiểm thử đang bắt đầu.
8. Nhấn **Job ID**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.6testing/4.1.6.5testing.png?width=90pc)

9. Khám phá **Job log** để thấy chi tiết.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.6testing/4.1.6.6testing.png?width=90pc)

10. Khi khởi tạo công việc hoàn tất, bạn nên thấy trạng thái thựctế của kết quả khởi tạo mỗi máy chủ trong **Source servers**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.6testing/4.1.6.7testing.png?width=90pc)

11. Sau khi thực hiện tất cả các quy trình kiểm tra cần thiết trên các phiên bản kiểm tra mới này, hãy chọn tất cả 2 máy chủ.
12. Chọn **Test and cutover**.
13. Sau đó đánh dấu chúng **Ready for Cutover**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.6testing/4.1.6.8testing.png?width=90pc)

14. Nhấn **Continue**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.6testing/4.1.6.9testing.png?width=90pc)

15. Trạng thái của **Migration lifecycle** đổi thành **Ready for cutover**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.6testing/4.1.6.10testing.png?width=90pc)

Khi tất cả việc kiểm thử hoàn tất và các máy chủ được đánh dấu là **Ready for cutover**, di chuyển đến bước tiếp theo để hoàn thiện các thay đổi trong môi trường nguồn trước khi nó chuyển đổi.
