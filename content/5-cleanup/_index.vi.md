---
title : "Dọn dẹp tài nguyên "
date : "`r Sys.Date()`"
weight : 5
chapter : false
pre : " <b> 5. </b> "
---
### DMS Tasks
1. Đi đến [Database migration tasks](https://us-west-2.console.aws.amazon.com/dms/v2/home?region=us-west-2#tasks).
2. Chọn các tác vụ chứa **wordpress** trong tên, nhấn **Actions** và **Delete**. Sau đó, nhấn lại **Delete** để xác nhận.

### DMS Endpoints
1. Đi đến [DMS endpoint](https://us-west-2.console.aws.amazon.com/dms/v2/home?region=us-west-2#endpointList).
2. Chọn tất cả endpoint có chứa **wordpress** trong tên, nhấn **Actions** và **Delete**. Sau đó, nhấn lại **Delete** để xác nhận.

### DMS Replication Instances
1. Đi đến [DMS replication instances](https://us-west-2.console.aws.amazon.com/dms/v2/home?region=us-west-2#replicationInstances).
2. Chọn tất cả Replication Instances với tên bắt đầu bằng **mid** và chứa **wordpress**, nhấn **Actions** và **Delete**.  Sau đó, nhấn lại **Delete** để xác nhận.

### DMS Subnet Groups
1. Đi đến [DMS subnet groups](https://us-west-2.console.aws.amazon.com/dms/v2/home?region=us-west-2#subnetGroup).
2. Chọn tất cả Subnet Groups chứa tên **wordpress**, nhấn **Actions** và **Delete**.  Sau đó, nhấn lại **Delete** để xác nhận.

### RDS WordPress
1. Đi đến [RDS](https://us-west-2.console.aws.amazon.com/rds/home?region=us-west-2#databases:).
2. Mở rộng **mid-wordpress** và chọn máy chủ **Writer**. Sau đó, đi đến **Actions** và chọn **Delete**.
3. Vì đây chỉ là một bài thực hành, chúng ta sẽ không tạo bản snapshot. Nhưng, trong môi trường thực tế, đây là một ý tưởng tốt. Và sau đó, để xác nhận lại việc xóa, nhập ```delete me``` và nhấn xóa.

### Onprem EC2 Instances (MGN and DMS)
1. Đi đến [EC2](https://us-west-2.console.aws.amazon.com/ec2/home?region=us-west-2#Instances:).
2. Thêm **MID** , **onpremsim.env** và **MGN** vào bộ lọc. Sau đó, chọn tất cả các máy chủ được liệt kê trong bộ lọc.
3. Nhấn **Actions**, nhấn **Instance State** và nhấn **Terminate**.

### CloudFormation
1. Đi đến [CloudFormation](https://us-west-2.console.aws.amazon.com/cloudformation/home?region=us-west-2#/stacks?filteringText=&filteringStatus=active&viewNested=true).
2. Chọn stack tên **FCJ-MigrationHub-Workshop**, và nhấn **Delete**.
3. Nếu xảy ra lỗi, thực hiện xóa từng stack thủ công.

### Volume and snapshot
1. Đi đến [EBS Volume](https://us-west-2.console.aws.amazon.com/ec2/home?region=us-west-2#Volumes:) và [EBS Snapshot](https://us-west-2.console.aws.amazon.com/ec2/home?region=us-west-2#Snapshots:).
2. Chọn và thực hiện xóa bản chụp và ổ đĩa được tạo bởi MGN cho các máy chủ liên quan đến bài thực hành này.