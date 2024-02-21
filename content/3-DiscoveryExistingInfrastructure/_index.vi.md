---
title : "Khám phá hạ tầng hiện có"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 3. </b> "
---

### Tổng quan
[AWS Application Discovery Service](https://docs.aws.amazon.com/application-discovery/latest/userguide/what-is-appdiscovery.html) giúp doanh nghiệp khách hàng lên kế hoạch dịch chuyển các dự án bằng việc thu thập thông tin về các trung tâm dữ liệu tại chỗ của họ.

[The AWS Application Discovery Agent](https://docs.aws.amazon.com/application-discovery/latest/userguide/discovery-agent.html) là phần mềm mà bạn cài vào các VMs và máy chủ tại chỗ mục tiêu cho khám phá và dịch chuyển. Agents thu thập cấu hình hệ thống, hiệu năng của hệ thống, các quy trình hoạt động, và chi tiết về kết nối mạng giữa các hệ thống. Agents hỗ trợ hầu hết các hệ điều hành Linux và Windows, và bạn có thể triển khai chúng trong các máy chủ vật lí tại chỗ, máy chủ Amazon EC2, và máy ảo. 

The Discovery Agent chạy trong môi trường cục bộ và yêu cầu quyền root. Khi bạn khởi động Discovery Agent, nó sẽ đăng ký với Application Discovery Service endpoint, arsenal-discovery..amazonaws.com, và gọi dịch vụ trong khoảng thời gian 15 phút để biết thông tin cấu hình. Khi bạn gửi lệnh yêu cầu một agent bắt đầu thu thập dữ liệu, nó sẽ bắt đầu thu thập dữ liệu cho máy chủ hoặc VM nơi nó cư trú. Việc thu thập bao gồm thông số kỹ thuật của hệ thống, dự liệu hiệu suất hoặc mức sử dụng theo thời gian, kết nối mạng và quy trình dữ liệu. Bạn có thể sử dụng thông tin này để  lập bản đồ tài sản CNTT của mình và các phần phụ thuộc mạng của chúng. Tất cả các điểm dữ liệu này có thể giúp bạn xác định chi phí vận hành các máy chủ này trong AWS cũng như lập kế hoạch di chuyển.

Dữ liệu được truyền một cách an toàn từ Discovery Agents đến Application Discovery Service sử dụng mã hóa Transport Layer Security (TLS). Agents được cấu hình để nâng cấp tự động khi phiên bản mới khả dụng. Bạn có thể thay đổi cài đặt cấu hình này nếu muốn.

### Nội dung
+ 3.1 [Kích hoạt tích hợp Athena](../3-discoveryexistinginfrastructure/3.1-enableathenaintegration/)
+ 3.2 [Tải ADS Agent cho VMs](../3-discoveryexistinginfrastructure/3.2-installadsagenttovms/)
+ 3.3 [Duyệt qua dữ liệu được khám phá](../3-discoveryexistinginfrastructure/3.3-browsediscovereddata/)
+ 3.4 [Trực quan kết nối mạng](../3-discoveryexistinginfrastructure/3.4-viewingnetworkconnections/)
+ 3.5 [Bảng khuyến nghị máy chủ EC2 ](../3-discoveryexistinginfrastructure/3.5-ec2instancerecommendations/)
+ 3.6 [Khám phá dữ liệu sử dụng Athena](../3-discoveryexistinginfrastructure/3.6-exploredatausingathena/)
