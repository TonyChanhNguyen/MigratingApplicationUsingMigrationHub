---
title : "Dịch chuyển ứng dụng sử dụng Migration Hub"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 1. </b> "
---
# Dịch chuyển ứng dụng sử dụng Migration Hub
### Tổng quan
Trong bài thực hành này chúng ta sẽ khám phá và dịch chuyển một môi trường sản phẩm mô phỏng chạy trên trung tâm dữ liệu của khách hàng. Môi trường này bao gồm 2 ứng dụng và 4 máy chủ.

Tất cả nội dụng áp dụng trong bài thực hành này cũng có thể được áp dụng cho quy mô dịch chuyển 10, 100, hoặc hàng ngàn máy chủ.

![Lab architecture](../images/architecture.png?width=80pc)

Bài thực hành này sử dụng một môi trường mô phỏng tại chỗ với các máy chủ ảo EC2, được cấu hình theo cách bắt chước một môi trường của khách hàng, với hạ tầng mạng nội bộ và công khai, máy chủ DNS, ứng dụng được cài sẵn và một Bastion Host.

Bây giờ, chúng ta sẽ khám phá và dịch chuyển 4 máy chủ này từ môi trường mô phỏng tại chỗ lên hạ tầng AWS.

### Để thực hiện bài thực hành này, người tham gia được yêu cầu phải quen thuộc với: 
+ Kết nối tới một máy chủ Microsoft Windows sử dụng Remote Desktop Protocol (RDP)
+ Kết nối tới máy chủ Linux sử dụng Putty
+ Câu lệnh Linux Bash cơ bản 
+ Câu lệnh Windows PowerShell cơ bản 
+ Bảng điều khiển AWS 
+ Cơ bản DNS và phân giải tên miền
+ Các dịch vụ AWS AWS (EC2, CloudFormation)

### Tài nguyên cần có:
+ Một máy tính cá nhân (Linux, Windows hoặc Mac)
+ Kết nối internet với truy cập bên ngoài tới phương thức RDP (TCP port 3389).
+ Một tài khoản AWS khả dụng.


### Khi kết thúc bài thực hành này, bạn sẽ:
+ Hiểu công việc như thế nào để dịch chuyển một dự án
+ Khám phá các máy chủ và ứng dụng sử dụng AWS Application Discovery Service
+ Nhóm các máy chủ lại thành ứng dụng sử dụng AWS Migration Hub
+ Dịch chuyển máy chủ với MGN
+ Dịch chuyển cơ sở dữ liệu với AWS Database Migration Service

 {{%notice warning%}}
Chi phí dụ trù cho các tài nguyên AWS cho bài thực hành này khoảng từ  USD$10 đến USD$15 cho khoảng 8 giờ thực hành. Đảm bảo tắt tất cả CloudFormation và xóa tất cả các tài nguyên được tạo trong bài thực hành này sau khi hoàn tất.
{{%/notice%}}
