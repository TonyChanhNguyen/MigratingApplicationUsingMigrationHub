---
title : "Tắt máy chủ nguồn và cập nhật DNS"
date :  "`r Sys.Date()`" 
weight : 4.2.6
chapter : false
pre : " <b> 4.2.6 </b> "
---

Bây giờ tất cả CSDL của bạn đã được dịch chuyển lên Aurora, đây là thời điểm để cập nhật thông tin DNS để máy chủ ứng dụng có thể kết nối tới máy chủ CSDL Aurora. Cả hai ứng dụng đều đang sử dụng DNS làm tên máy chủ kết nối. Trong dịch chuyển ứng dụng thực tế, khi bạn hoàn tất tất cả kiểm thử của bạn và sẵn sàng chuyển đổi hoàn toàn lên CSDL Aurora, bạn nên thực hiện tắt các máy chủ nguồn và cập nhật bản ghi DNS đúng cách để phản ánh đến máy chủ CSDL mới chạy trong Aurora.

1. Từ Bastion Host, SSH đến máy chủ tên **wordpress-db**.
2. Kiểm tra bản ghi DNS CSDL hiện tại bằng cách chạy các dòng lệnh từ Putty:
```
nslookup wordpress-db
```

3. Tạo biến tên (ADDR) sử dụng điểm cuối RDS. Xem lại bước 25 của [Create Aurora final target database](../4.2.1-CreateAuroraFinalTargetDatabases/).
```
ADDR="<REPLACE THIS WITH WORDPRESS ENDPOINT>"
```
4. Sau đó, chạy lệnh dưới đây để cập nhật bản ghi DNS:
```
HOST="wordpress-db.onpremsim.env"
sudo touch /tmp/nsupdate.txt
sudo chmod 666 /tmp/nsupdate.txt
echo "server dns.onpremsim.env" > /tmp/nsupdate.txt
echo "update delete $HOST A" >> /tmp/nsupdate.txt
echo "update delete $HOST PTR" >> /tmp/nsupdate.txt
echo "update add $HOST 86400 CNAME $ADDR." >> /tmp/nsupdate.txt
echo "send" >> /tmp/nsupdate.txt
sudo nsupdate /tmp/nsupdate.txt
```
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.6shutdown/4.2.6.1shutdown.png?width=90pc)

5. Xác minh lại độ phân giải tên DNS.
```
nslookup wordpress-db
```
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.6shutdown/4.2.6.2shutdown.png?width=90pc)

CNAME đã được cập nhật để được trỏ tới CSDL Aurora (so sánh kết quả đầu ra với bước trước đó).
6. Tắt máy chủ CSDL nguồn.
```
sudo shutdown -h now
```
7. Từ máy chủ Bastion Host, kiểm tra ứng dụng của bạn sử dụng trình duyệt web với đường dẫn URL http://wordpress-web.onpremsim.env/.

#### Đây là màn hình mong đợi nếu dịch chuyển thành công:
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.6shutdown/4.2.6.3shutdown.png?width=80pc)

### Chúc mừng, bạn vừa dịch chuyển các máy chủ của doanh nghiệp bạn lên AWS thành công.