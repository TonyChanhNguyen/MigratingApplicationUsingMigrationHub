---
title : "Khám phá dữ liệu sử dụng Athena    "
date :  "`r Sys.Date()`" 
weight : 6 
chapter : false
pre : " <b> 3.6 </b> "
---
Sau khi bật Data Exploration trong Amazon Athena, bạn có thể bắt đầu khám phá và làm việc với dữ liệu chi tiết trong Amazon Athena. Bạn có thể truy vấn dữ liệu này trực tiếp trong Athena để thực hiện những việc như tạo bảng tính, chạy phân tích chi phí, chuyển truy vấn sang chương trình trực quan hóa để lập sơ đồ các phần phụ thuộc của mạng, và hơn thế nữa.

### Tìm hiểu ADS Database trong Athena
1. Đi đến [Server of Migration Hub](https://us-west-2.console.aws.amazon.com/migrationhub/home?region=us-west-2#/discover/servers).
2. Nhấn nút **Actions**.
3. Sau đó nhấn **View in Amazon Athena**.
![Explore data using Athena](../../../images/3.discoveryexistinginfra/3.6exploredata/3.6.1exploredata.png?width=90pc)

4. Tại trang **Query editor**, chọn tab **Settings**.
![Explore data using Athena](../../../images/3.discoveryexistinginfra/3.6exploredata/3.6.2exploredata.png?width=90pc)

5. Sau đó, nhấn **Manage**.
![Explore data using Athena](../../../images/3.discoveryexistinginfra/3.6exploredata/3.6.3exploredata.png?width=90pc)

6. Tại trang **Manage settings**, nhấn **Browse S3**.
![Explore data using Athena](../../../images/3.discoveryexistinginfra/3.6exploredata/3.6.4exploredata.png?width=90pc)

7.  Chọn tên S3 bucket **aws-application-discovery-service-xxxxxxxxxxxxxxxxxxxxxxxxx**.
8. Sau đó, chọn **Choose**.
![Explore data using Athena](../../../images/3.discoveryexistinginfra/3.6exploredata/3.6.5exploredata.png?width=90pc)

9. Sau đó, nhấn **Save**.
![Explore data using Athena](../../../images/3.discoveryexistinginfra/3.6exploredata/3.6.6exploredata.png?width=90pc)

10. Trong tab **Editor**, ở thanh chuyển hướng bên dưới **Database**, đảm bảo rằng *application_discovery_service_database* được chọn.
![Explore data using Athena](../../../images/3.discoveryexistinginfra/3.6exploredata/3.6.7exploredata.png?width=90pc)

11. Bên dưới **Tables** các bảng sau đây biểu thị các tập dữ liệu được nhóm theo các agents.
+ os_info_agent
+ network_interface_agent
+ sys_performance_agent
+ processes_agent
+ inbound_connection_agent
+ outbound_connection_agent
+ id_mapping_agent
![Explore data using Athena](../../../images/3.discoveryexistinginfra/3.6exploredata/3.6.8exploredata.png?width=90pc)

### Khám phá dữ liệu thu thập được với truy vấn dựng sẵn.
1. Thêm mã truy vấn vào cửa sổ **Athena's Query Editor**.
2. Chọn **Run** để thấy kết quả.

```
CREATE OR REPLACE VIEW hostname_ip_helper AS
SELECT DISTINCT
  "os"."host_name"
, "nic"."agent_id"
, "nic"."ip_address"
FROM
  os_info_agent os
, network_interface_agent nic
WHERE ("os"."agent_id" = "nic"."agent_id");
```
![Explore data using Athena](../../../images/3.discoveryexistinginfra/3.6exploredata/3.6.9exploredata.png?width=90pc)

3. Để xem truy vấn này trông như thế nào, tìm phần **Views** bên dưới **Tables** của bạn. 
4. Nhấn vào mục 3 chấm và chọn **Preview View**.
![Explore data using Athena](../../../images/3.discoveryexistinginfra/3.6exploredata/3.6.10exploredata.png?width=90pc)

5. Quan sát kết quả.
![Explore data using Athena](../../../images/3.discoveryexistinginfra/3.6exploredata/3.6.11exploredata.png?width=90pc)

#### Xác định máy chủ có hoặc không có Agents
Truy vấn này có thể giúp bạn thực hiện xác thực dữ liệu. Nếu bạn đã triển khai agent trên một số máy chủ trong mạng của mình, bạn có thể sử dụng truy vấn này để tìm hiểu xem có máy chủ nào khác trong mạng của bạn mà không có agent được triển khai trên chúng hay không. Trong truy vấn này, chúng tôi xem xét lưu lượng truy cập mạng vào và ra và chỉ lọc lưu lượng truy cập cho các địa chỉ IP riêng tư. Tức là địa chỉ IP bắt đầu bằng 192, 10 hoặc 172.
```
SELECT DISTINCT "destination_ip" "IP Address" ,
         (CASE
    WHEN (
    (SELECT "count"(*)
    FROM network_interface_agent
    WHERE ("ip_address" = "destination_ip") ) = 0) THEN
        'no'
        WHEN (
        (SELECT "count"(*)
        FROM network_interface_agent
        WHERE ("ip_address" = "destination_ip") ) > 0) THEN
            'yes' END) "agent_running"
    FROM outbound_connection_agent
WHERE ((("destination_ip" LIKE '192.%')
        OR ("destination_ip" LIKE '10.%'))
        OR ("destination_ip" LIKE '172.%'))
UNION
SELECT DISTINCT "source_ip" "IP ADDRESS" ,
         (CASE
    WHEN (
    (SELECT "count"(*)
    FROM network_interface_agent
    WHERE ("ip_address" = "source_ip") ) = 0) THEN
        'no'
        WHEN (
        (SELECT "count"(*)
        FROM network_interface_agent
        WHERE ("ip_address" = "source_ip") ) > 0) THEN
            'yes' END) "agent_running"
    FROM inbound_connection_agent
WHERE ((("source_ip" LIKE '192.%')
        OR ("source_ip" LIKE '10.%'))
        OR ("source_ip" LIKE '172.%'));

```
![Explore data using Athena](../../../images/3.discoveryexistinginfra/3.6exploredata/3.6.12exploredata.png?width=90pc)

#### Phân tích dữ liệu hiệu suất hệ thống cho các máy chủ có agent
Bạn có thể sử dụng truy vấn này để phân tích hiệu suất hệ thống và dữ liệu mẫu sử dụng cho các máy chủ tại chỗ có cài đặt tác nhân trên đó. Truy vấn kết hợp bảng system_performance_agent với bảng os_info_agent để xác định tên máy chủ cho mỗi máy chủ. Truy vấn này trả về dữ liệu sử dụng chuỗi thời gian (trong khoảng thời gian 15 phút) cho tất cả các máy chủ nơi tác nhân đang chạy.
```
SELECT "OS"."os_name" "OS Name" ,
     "OS"."os_version" "OS Version" ,
     "OS"."host_name" "Host Name" ,
     "SP"."agent_id" ,
     "SP"."total_num_cores" "Number of Cores" ,
     "SP"."total_num_cpus" "Number of CPU" ,
     "SP"."total_cpu_usage_pct" "CPU Percentage" ,
     "SP"."total_disk_size_in_gb" "Total Storage (GB)" ,
     "SP"."total_disk_free_size_in_gb" "Free Storage (GB)" ,
     ("SP"."total_disk_size_in_gb" - "SP"."total_disk_free_size_in_gb") "Used Storage" ,
     "SP"."total_ram_in_mb" "Total RAM (MB)" ,
     ("SP"."total_ram_in_mb" - "SP"."free_ram_in_mb") "Used RAM (MB)" ,
     "SP"."free_ram_in_mb" "Free RAM (MB)" ,
     "SP"."total_disk_read_ops_per_sec" "Disk Read IOPS" ,
     "SP"."total_disk_bytes_written_per_sec_in_kbps" "Disk Write IOPS" ,
     "SP"."total_network_bytes_read_per_sec_in_kbps" "Network Reads (kbps)" ,
     "SP"."total_network_bytes_written_per_sec_in_kbps" "Network Write (kbps)"
FROM "sys_performance_agent" "SP" , "OS_INFO_agent" "OS"
WHERE ("SP"."agent_id" = "OS"."agent_id") limit 10;

```
![Explore data using Athena](../../../images/3.discoveryexistinginfra/3.6exploredata/3.6.13exploredata.png?width=90pc)