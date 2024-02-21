---
title : "Dịch chuyển hạn tầng"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 4.1 </b> "
---

### MGN
[AWS Application Migration Service (AWS MGN)](https://aws.amazon.com/application-migration-service/) là một giải phát tự động hóa cao giúp đơn giản hóa, đẩy nhanh và giảm chi phí dịch chuyển và hiện đại hóa ứng dụng. Nó cho phép các công ty dịch chuyển lượng lớn máy chủ vật lý, ảo và đám mây mà không gặp vấn đề về tương thích, gián đoạn hiệu năng hoặc thời gian chuyển đổi dài. AWS MGN nhân bản liên tục máy chủ nguồn vào tài khoản AWS của bạn. Khi bạn sẵn sàng, nó sẽ tự động chuyển đổi và khởi chạy các máy chủ bên trong AWS để bạn có thể nhanh chóng hưởng lợi từ việc tiết kiệm chi phí, năng suất, khả năng phục hồi và tính linh hoạt của điện toán đám mây. Ngoài ra, AWS MGN cho phép bạn hiện đại hóa các ứng dụng đã khởi tạo bằng cách chạy cách hành động được cấu hính sẵn.


### Nó hoạt động như thế nào?
![Migrating your application](../../../images/4.migrateinfra/4.1migrateapp/4.1.1migrateapp.png?width=90pc)

### Lợi ích của Application Migration Service bao gồm:
+ Thời gian chuyển đổi trong vài phút và không mất dữ liệu
+ Dịch chuyển quy mô lớn mà không ảnh hưởng đến hiệu năng
+ Hổ trợ các hệ điều hành và nền tảng rộng lớn
+ Tự động hóa việc dịch chuyển để giảm thiểu tài nguyên và thời gian thực hiện dự án CNTT.

### Nội dung
+ 4.1.1 [Cấu hình dịch vụ AWS MGN](4.1.1-configureawsmgnservi)
+ 4.1.2 [Cấu hình target template mặc định](4.1.2-configuredefaulttargettemplat)
+ 4.1.3 [Tạo IAM user cho AWS replication agent](4.1.3-createawsreplicationagentiamus)
+ 4.1.4 [Tải AWS replication agent](4.1.4-installawsreplicationage)
+ 4.1.5 [AWS MGN migration lifecycle](4.1.5-awsmgnmigrationlifecyc)
+ 4.1.6 [Triển khai máy chủ kiểm thử](4.1.6-launchtestinstan)
+ 4.1.7 [Tắt môi trường nguồn](4.1.7-shutdownsourceenvironme)
+ 4.1.8 [Triển khai máy chủ chuyển đổi](4.1.8-launchcutoverinstan)
+ 4.1.9 [Cập nhật DNS và xác nhận các ứng dụng](4.1.9-updatednsandvalidatetheapplicatio)
+ 4.1.10 [Hoàn thiện chuyển đổi và lưu trữ máy chủ](4.1.10-finalizecutoverandarchiveserve)
