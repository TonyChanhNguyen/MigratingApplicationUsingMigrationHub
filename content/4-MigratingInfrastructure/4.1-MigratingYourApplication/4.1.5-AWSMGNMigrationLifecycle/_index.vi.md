---
title : "AWS MGN migration lifecycle"
date :  "`r Sys.Date()`" 
weight : 5
chapter : false
pre : " <b> 4.1.5  </b> "
---
Bây giờ bạn có thể giám sát quy trình nhân bản để hiểu khi quá trình dịch chuyển của bạn được hoàn tất bởi AWS MGN Migration Life Cycle.
1. Nhấn **Source server name** tên **ofbiz-web.onpremsim.env**.
![Migrating your application](../../../../images/4.migrateinfra/4.1migrateapp/4.1.5lifecycle/4.1.5.1lifecycle.png?width=90pc)

2. Bây giờ, quá trình dịch chuyển của máy chủ này đang ở bước **Not ready**.
![Migrating your application](../../../../images/4.migrateinfra/4.1migrateapp/4.1.5lifecycle/4.1.5.2lifecycle.png?width=90pc)

Vòng đời (Life Cycle) thể hiện trạng thai hiện tại của mỗi máy chủ bên trong vòng đời dịch chuyển. Và có 6 trạng thái của dòng đời dịch chuyển:

+ Not ready - Máy chủ đang trong quá trình thực hiện Initial Sync và vẫn chưa sẵn sàng cho việc kiểm thử. Quy trình này mất vài giờ đến vài ngày tùy thuộc vào tốc độ mạng và kích cỡ của máy chủ nguồn.
+ Ready for testing - Máy chủ được thêm thành công vào Application Migration Service và Initial Sync đã hoàn tất. Phiên bản kiểm thử hoặc chuyển đổi có thể được khởi tạo ngay bây giờ cho các máy chủ này
+ Test in progress - Một phiên bản kiểm thử hiện tại đang được khởi tạo cho máy chủ này. Lưu ý rằng có một liên kết đến Job ID của công việc được khởi chạy kết nối với việc khởi chạy phiên bản này.
+ Ready for cutover - Máy chủ này đac được kiểm thử và sẵn sàng cho một phiên bản chuyển đổi được khởi tạo
+ Cutover in progress - Phiên bản chuyển đổi đang được khởi tạo trên máy chủ này. Lưu ý rằng có một liên kết đến Job ID của công việc được khởi chạy kết nối với việc khởi chạy phiên bản này.
+ Cutover complete - Dịch chuyển máy chủ này đã được hoàn tất. Tất cả tài nguyên liên kết tới dịch chuyển của máy chủ này đã được dọn dẹp.
