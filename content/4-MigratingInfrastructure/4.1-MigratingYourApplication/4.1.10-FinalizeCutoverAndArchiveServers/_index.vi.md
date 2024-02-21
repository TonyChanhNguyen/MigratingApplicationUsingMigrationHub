---
title : "Hoàn thiện chuyển đổi và lưu trữ máy chủ"
date :  "`r Sys.Date()`" 
weight : 10
chapter : false
pre : " <b> 4.1.10 </b> "
---

### Hoàn thiện chuyển đổi

Khi quy trình chuyển đổi hoàn tất và bạn không cần phải sao lưu dữ liệu trong khu vực Staging, bạn có thể hoàn tất chuyển đổi. Điều này sẽ xóa bỏ tất các các tài nguyên được tạo trong quá trình dịch chuyển và dọn dẹp khu vực Staging.
1. Đi đến [Source servers](https://us-west-2.console.aws.amazon.com/mgn/home?region=us-west-2#/sourceServers).
2. Chọn 2 máy chủ.
3. Nhấn **Test and cutover**.
4. Chọn **Finalize cutover**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.10cutover/4.1.10.1cutover.png?width=90pc)

5. Nhấn **Finalize**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.10cutover/4.1.10.2cutover.png?width=90pc)

6. Trạng thái của **Migration lifecycle** chuyển thành **Cutover complete**, trạng thái của **Data replication** chuyển thành **Disconnected**, và cột **Alerts** hiện cảnh báo cuối cùng **Launched**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.10cutover/4.1.10.4cutover.png?width=90pc)

Bây giờ tất cả máy chủ đã được chuyển đổi và hoàn thiện, bạn có thể lưu trữ các máy chủ này để xóa bỏ chúng từ danh sách máy chủ nguồn kích hoạt.
### Lưu trữ các máy chủ vừa được dịch chuyển
Bây giờ bạn có thể lưu trữ máy chủ nguồn đã được khởi tạo phiên bản chuyển đổi. Việc lưu trữ sẽ xóa bỏ những máy chủ nguồn từ trang Source Servers, cho phép chúng ta tập trung vào các máy chủ nguồn chưa được chuyển đổi. Bạn sẽ vẫn có thể truy cập các máy chủ lưu trữ thông qua bộ lọc.
1. Chọn hai máy chủ.
2. Nhấn **Action**.
3. Chọn **Mark as archived**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.10cutover/4.1.10.5cutover.png?width=90pc)

4. Nhấn **Archive**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.10cutover/4.1.10.6cutover.png?width=90pc)

5. Để thấy các máy chủ được lưu trữ của bạn, mở mục thả xuống bên dưới và chọn **Archived source servers**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.10cutover/4.1.10.7cutover.png?width=90pc)
