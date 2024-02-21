---
title : "Trực quan kết nối mạng"
date :  "`r Sys.Date()`" 
weight : 4 
chapter : false
pre : " <b> 3.4 </b> "
---
Xem các kết nối mạng trong AWS Migration Hub cho phép bạn trực quan hóa các phần phụ thuộc của máy chủ. Việc trực quan hóa các phần phụ thuộc này giúp bạn xác minh tất cả tài nguyên cần thiết để di chuyển thành công từng ứng dụng của bạn sang Amazon Web Services.

Bạn xem kết nối mạng bằng cách sử dụng sơ đồ mạng. Khi sử dụng sơ đồ mạng, bạn có thể xem xét trực quan lượng lớn dữ liệu để hiểu những gì phụ thuộc vào máy chủ tồn tại. Việc hiểu rõ các phần phụ thuộc của máy chủ này sẽ giúp bạn lập kế hoạch về cách nhóm các tài nguyên cần thiết lại với nhau để hỗ trợ ứng dụng di chuyển sang AWS.
1. Tại mục [Server](https://us-west-2.console.aws.amazon.com/migrationhub/home?region=us-west-2#/discover/servers) của **Migration Hub**.
2. Chọn tất cả máy chủ và nhấn **Visualize network**.
![Visualize Network](/images/3.discoveryexistinginfra/3.4visualizenetwork/3.4.1visualizenetwork.png?width=90pc)

3. Vì chúng ta đã chọn tất cả các máy chủ nên bạn sẽ thấy sơ đồ mô tả cách chúng liên quan với nhau, có thể mất vài phút để cập nhật các mối quan hệ này.
![Visualize Network](/images/3.discoveryexistinginfra/3.4visualizenetwork/3.4.2visualizenetwork.png?width=90pc)

4. Trong một số môi trường, việc xem toàn bộ mạng trên cùng một sơ đồ có thể khiến bạn choáng ngợp. Chúng ta hãy quay lại tab Server list và chọn máy chủ  *wordpress-web* để xem xét kỹ hơn. Chọn phiên bản và nhấp vào tab Network.
![Visualize Network](/images/3.discoveryexistinginfra/3.4visualizenetwork/3.4.3visualizenetwork.png?width=90pc)

5. Biểu tượng máy chủ bạn chọn nằm ở giữa sơ đồ mạng. Các kết nối được phân bổ từ máy chủ trung tâm đến các máy chủ được kết nối trực tiếp với máy chủ bạn chọn.
![Visualize Network](/images/3.discoveryexistinginfra/3.4visualizenetwork/3.4.4visualizenetwork.png?width=90pc)

Bây giờ chúng ta thấy rõ rằng máy chủ này có sự phụ thuộc với máy chủ wordpress-db. Ngoài ra, chúng ta có thể nhận thấy rằng nó cũng đang liên lạc với 192.168.0.246 (máy chủ Bastion) và 192.168.1.250 (máy chủ DNS).

6. Chúng ta sẽ nhóm *wordpress-web* và *wordpress-db* với nhau chúng vì bao gồm mặt trước và mặt sau của ứng dụng. Quay trở lại Server list tab và chọn 2 máy chủ đó.
7. Sau đó nhấn **Group as application**.
![Visualize Network](/images/3.discoveryexistinginfra/3.4visualizenetwork/3.4.5visualizenetwork.png?width=90pc)

8. Chọn **Group as a new application**.
9. Nhập **Application name** ```Wordpress```.
10. Nhấn **Group**.
![Visualize Network](/images/3.discoveryexistinginfra/3.4visualizenetwork/3.4.6visualizenetwork.png?width=90pc)

11. Tạo một nhóm ứng dụng cho ứng dụng **ofbiz**  bao gồm 2 máy chủ ofbiz.
![Visualize Network](/images/3.discoveryexistinginfra/3.4visualizenetwork/3.4.7visualizenetwork.png?width=90pc)

 {{%notice info%}}
Với môi trường sản phẩm thực tế thì khuyến cáo dữ liệu máy chủ Discovery Agent nên được thu thập từ 2 đến 6 tuần trước khi bạn có thể sử dụng sơ đồ mạng để xem các mẫu kết nối được thiết lập.
{{%/notice%}}

