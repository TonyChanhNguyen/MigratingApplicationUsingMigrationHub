---
title : "Tắt môi trường nguồn"
date :  "`r Sys.Date()`" 
weight : 7 
chapter : false
pre : " <b> 4.1.7 </b> "
---
Trong dịch chuyển ứng dụng thực tế, khi bạn hoàn tất tất cả việc kiểm thử và sẵn sàng để chuyển đổi hoàn toàn máy chủ của bạn lên đám mây, bạn nên thực hiệu việc tắt và chấm dứt các máy chủ nguồn và cập nhật bản ghi DNS đúng cách để phản ánh các máy chủ mới đang chạy trên đám mây.
1. Từ Bastion host, kết nối tới máy chủ ofbiz-web and ofbiz-db sử dụng SSH.
2. Tắt các máy chủ nguồn đang chạy trông môi trường tại chỗ theo hướng dẫn sau:
```
sudo shutdown -h now
```
Sau khi môi trường nguồn tắt, tất cả các thay đổi cuối cùng từ hệ thống nguồn sẽ được sao chép đến khu vực Staging, và chúng ta sẵn sàng cho việc chuyển đổi cuối cùng.

3. Đi đến [Source servers](https://us-west-2.console.aws.amazon.com/mgn/home?region=us-west-2#/sourceServers). Lưu ý rằng cột **Alert** trạng thái chuyển thành **Lagging** sau khi hệ thống nguồn tắt.

![Migrating your application](../../../../images/4.migrateinfra/4.1migrateapp/4.1.7shutdown/4.1.7.1shutdown.png?width=90pc)

Sau một vài phút, cả cột **Alerts** và **Data replication status** sẽ thay đổi trạng thái máy chủ thành **Stalled**. Điều này được mong đợi khi dừng tất cả các máy chủ nguồn và quy trình nhân bản bị ngừng. Tuy nhiên, tất cả dữ liệu từ máy chủ nguồn đã hoàn toàn được đồng bộ đến ổ đĩa EBS trong khu vực **Staging**, và bây giờ máy chủ chuyển đổi cuối cùng khi khởi tạo sẽ có những dữ liệu mới nhất từ hệ thống nguồn
![Migrating your application](../../../../images/4.migrateinfra/4.1migrateapp/4.1.7shutdown/4.1.7.2shutdown.png?width=90pc)