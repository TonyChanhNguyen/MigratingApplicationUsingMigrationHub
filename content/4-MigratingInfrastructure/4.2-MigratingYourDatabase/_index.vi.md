---
title : "Dịch chuyển cơ sở dữ liệu của bạn"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 4.2 </b> "
---

### AWS Database Migration Services
Bây giờ bạn vừa hoàn tất việc di chuyển ứng dụng của mình sang AWS bằng MGN, hãy di chuyển cơ sở dữ liệu để chạy trong Amazon Aurora bằng công cụ AWS Database Migration Service.

giúp bạn di chuyển cơ sở dữ liệu sang AWS một cách nhanh chóng và an toàn. Cơ sở dữ liệu nguồn vẫn hoạt động đầy đủ trong quá trình di chuyển, giảm thiểu thời gian ngừng hoạt động đối với các ứng dụng dựa trên cơ sở dữ liệu. The AWS Database Migration Service có thể di chuyển dữ liệu của bạn đến và đi từ hầu hết các cơ sở dữ liệu thương mại và nguồn mở được sử dụng rộng rãi nhất.

AWS Database Migration Service hỗ trợ di chuyển đồng nhất như Oracle sang Oracle, cũng như di chuyển không đồng nhất giữa các nền tảng cơ sở dữ liệu khác nhau, chẳng hạn như Oracle hoặc Microsoft SQL Server sang Amazon Aurora. Với AWS Database Migration Service, bạn có thể liên tục sao chép dữ liệu của mình với độ khả dụng cao và hợp nhất cơ sở dữ liệu vào kho dữ liệu quy mô petabyte bằng cách truyền dữ liệu tới Amazon Redshift và Amazon S3.

Amazon Aurora là cơ sở dữ liệu quan hệ tương thích với MySQL và PostgreSQL được xây dựng cho đám mây, kết hợp hiệu suất và tính khả dụng của cơ sở dữ liệu doanh nghiệp truyền thống với tính đơn giản và hiệu quả về mặt chi phí của cơ sở dữ liệu nguồn mở.

Amazon Aurora nhanh hơn tới năm lần so với cơ sở dữ liệu MySQL tiêu chuẩn và nhanh hơn ba lần so với cơ sở dữ liệu PostgreSQL tiêu chuẩn. Nó cung cấp tính bảo mật, tính khả dụng và độ tin cậy của cơ sở dữ liệu thương mại với chi phí chỉ bằng 1/10. Amazon Aurora được quản lý hoàn toàn bởi Amazon Relational Database Service (RDS), dịch vụ này tự động hóa các tác vụ quản trị tốn nhiều thời gian như cung cấp phần cứng, thiết lập cơ sở dữ liệu, vá lỗi và sao lưu.

### Trong phần này, bạn sẽ thực hiện những nội dung sau:
+ Tạo CSDL Amazon Aurora
+ Dịch chuyển CDSL hiện tại (chạy trên EC2) lên Aurora với AWS DMS
+ Cập nhật bản ghi DNS để phản ánh sự dịch chuyển

### Content
+ 4.2.1 [Tạo cơ sở dữ liệu target Aurora cuối cùng](4-migratinginfrastructu4.2-migratingyourdataba4.2.1-createaurorafinaltargetdatabases)
+ 4.2.2 [Tạo replication subnet groups](4-migratinginfrastructu4.2-migratingyourdataba4.2.2-createreplicaitonsubnetgrou)
+ 4.2.3 [Tạo một replication instance](4-migratinginfrastructu4.2-migratingyourdataba4.2.3-createareplicationinstance)
+ 4.2.4 [Chỉ định endpoint của source và target](4-migratinginfrastructu4.2-migratingyourdataba4.2.4-specifysourceandtargetendpoints)
+ 4.2.5 [Tạo và giám sát các tác vụ](4-migratinginfrastructu4.2-migratingyourdataba4.2.5-createandmonitorthetas)
+ 4.2.6 [Tắt máy chủ nguồn và cập nhật DNS](4-migratinginfrastructu4.2-migratingyourdataba4.2.6-shutdownsourceserverandupdated)