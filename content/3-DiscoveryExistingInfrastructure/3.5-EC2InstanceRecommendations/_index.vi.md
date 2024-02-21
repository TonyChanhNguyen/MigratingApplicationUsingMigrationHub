---
title : "Bảng khuyến nghị máy chủ EC2"
date :  "`r Sys.Date()`" 
weight : 5 
chapter : false
pre : " <b> 3.5 </b> "
---

Chúng ta hãy cùng khám phá tính năng khuyến nghị máy chủ EC2 trong Migration Hub để ước tính chi phí vận hành các máy chủ hiện có của bạn trong AWS. Tính năng này phân tích chi tiết về từng máy chủ, bao gồm thông số kỹ thuật của máy chủ, CPU và dữ liệu sử dụng bộ nhớ. Sau đó, dữ liệu đã biên dịch sẽ được sử dụng để đề xuất loại phiên bản Amazon EC2 ít tốn kém nhất có thể xử lý khối lượng công việc hiệu năng hiện có.
### Điều kiện tiên quyết
Trước khi có thể nhận đề xuất phiên bản Amazon EC2, bạn phải có dữ liệu về máy chủ tại chỗ của mình trong Migration Hub. Dữ liệu này có thể đến từ các công cụ khám phá (AWS Application Discovery Agent hoặc Application Discovery Service Agentless Collector) hoặc từ Migration Hub import. Với mục tiêu của bài thực hành này. chúng ta sẽ sử dụng Application Discovery Agent.

##### Tổng quan về 3 lựa chọn:
1. [AWS Application Discovery Agent](https://docs.aws.amazon.com/application-discovery/latest/userguide/discovery-agent.html) là phần mềm bạn cài đặt trên máy chủ tại chỗ và máy ảo được nhắm mục tiêu để khám phá và dịch chuyển. Agents hỗ trợ hầu hết các hệ điều hành Linux và Windows, đồng thời bạn có thể triển khai chúng trên máy chủ vật lý tại chỗ, phiên bản Amazon EC2 và máy ảo.
2. [Application Discovery Service Agentless Collector](https://docs.aws.amazon.com/application-discovery/latest/userguide/agentless-collector.html) là một ứng dụng tại chỗ thu thập thông tin thông qua các phương pháp không cần tác nhân về môi trường tại chỗ của bạn. Bạn cài đặt Agentless Collector dưới dạng máy ảo (VM) trong môi trường VMware vCenter Server bằng tệp Open Virtualization Archive (OVA) file.
3. [AWS Migration Hub (Migration Hub) import](https://docs.aws.amazon.com/application-discovery/latest/userguide/discovery-import.html) ho phép bạn nhập trực tiếp thông tin chi tiết về môi trường tại chỗ của mình vào Migration Hub mà không cần sử dụng Agentless Collector hoặc Discovery Agent, để bạn có thể thực hiện đánh giá và lập kế hoạch di chuyển trực tiếp từ dữ liệu đã nhập của mình. Bạn cũng có thể nhóm các thiết bị của mình thành ứng dụng và theo dõi trạng thái di chuyển của chúng.

### Generating Amazon EC2 Recommendations:
1. Đi đến [Migration Hub](https://us-west-2.console.aws.amazon.com/migrationhub/home?region=us-west-2#/dashboard).
2. Tại mục **Asset**. Chọn **EC2 instance recommendations** .
![EC2 instance recommendations](/images/3.discoveryexistinginfra/3.5ec2recommendation/3.5.1ec2recommendation.png?width=90pc)
3. Tại trang  **EC2 instance recommendations**, chọn **Average utilization** bên dưới **Sizing preferences**.
4. Chọn **US West (Oregon)** tại **Region**.
5. Chọn **Shared instances** tại **Tenancy**.
6. Chọn **On-Demand** tại **Pricing model**.
7. Sau đó, nhấn **Export recommendations**.
![EC2 instance recommendations](/images/3.discoveryexistinginfra/3.5ec2recommendation/3.5.2ec2recommendation.png?width=90pc)

8. Khi quá trình hoàn tất, trình duyệt của bạn sẽ tự động tải xuống tệp lưu trữ nén (ZIP), chứa tệp có giá trị (CSV) cùng với các khuyến nghị của bạn.
9. Kiểm tra tệp khuyến nghị, có các phân tích và khuyến nghị cho hệ thống của bạn. Ví dụ: Khi bạn khiểm tra cột P tên Recommendation.EC2.Instance.Model, it recommend the model for each instance can be at least suitable with this system.  Nó khuyến cáo mô hình cho mỗi máy chủ tối thiểu phù hợp với hệ thống của bạn
|Server.HostName                |Mô hình hiện tại              |Mô hình khuyến nghị     |
|-------------------------------|------------------------------|------------------------|
| ofbiz-db.onpremsim.env        |t3.small                      |t3a.nano                |      
| ofbiz-web.onpremsim.env       |t3.medium                     |t3a.medium              |      
| wordpress-web.onpremsim.env   |t3.small                      |t3a.micro               |      
| wordpress-db.onpremsim.env    |t3.small                      |t3a.nano                |      

 {{%notice info%}}
Kết quả phân tích này chỉ đưa ra đề xuất và không bắt buộc bạn phải thực hiện thêm bất kỳ hành động nào. Các lựa chọn và tùy chọn cho (các) phiên bản EC2 của bạn được thực hiện theo quyết định riêng của bạn.
{{%/notice%}}
