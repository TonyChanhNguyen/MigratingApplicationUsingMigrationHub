---
title : "Tạo và giám sát các tác vụ"
date :  "`r Sys.Date()`" 
weight : 5 
chapter : false
pre : " <b> 4.2.5 </b> "
---
Một AWS Database Migration Service (AWS DMS) task là nơi mọi công việc diễn ra. Bạn chỉ định bảng (hoặc dạng xem) và lược đồ nào sẽ sử dụng cho quá trình di chuyển của mình cũng như bất kỳ quá trình xử lý đặc biệt nào, chẳng hạn như yêu cầu ghi nhật ký, dữ liệu bảng điều khiển và xử lý lỗi

Khi tạo một tác vụ di chuyển, bạn cần biết một số điều:

+ Trước khi có thể tạo tác vụ, bạn phải tạo điểm cuối nguồn, điểm cuối đích và phiên bản sao chép.
+ Bạn có thể chỉ định nhiều cài đặt tác vụ để điều chỉnh tác vụ di chuyển của mình. Bạn có thể thiết lập những điều này bằng cách sử dụng bảng điều hướng AWS Management Console, AWS Command Line Interface (AWS CLI), hoặc AWS DMS API. Các cài đặt này bao gồm chỉ định cách xử lý lỗi di chuyển, ghi nhật ký lỗi và thông tin bảng điều khiển.
+ Sau khi tạo một tác vụ, bạn có thể chạy tác vụ đó ngay lập tức. Các bảng mục tiêu với các định nghĩa siêu dữ liệu cần thiết sẽ được tạo và tải tự động, đồng thời bạn có thể chỉ định việc sao chép liên tục.
+ Mặc định, AWS DMS bắt đầu tác vụ của bạn ngay khi bạn tạo nó. Tuy nhiên, trong một vài trường hợp, bạn có thể muốn trì hoãn việc bắt đầu nhiệm vụ. Ví dụ, khi bạn sử dụng AWS CLI, bạn có thể có một quy trình tạo tác vụ và một quy trình khác bắt đầu tác vụ dựa trên một số sự kiện kích hoạt. Khi cần thiết, bạn có thể trì hoãn việc bắt đầu nhiệm vụ của mình.
+ Bạn có thể theo dõi, dừng hoặc khởi động lại các tác vụ bằng cách sử dụng bảng điều hướng AWS DMS, AWS CLI, hoặc AWS DMS API.

### Tạo tác vụ của bạn
1. Đi đến [Database migration tasks](https://us-west-2.console.aws.amazon.com/dms/v2/home?region=us-west-2#tasks).
2. Nhấn **Create task**.
![Migrate your database](../../../../images/4.migrateinfra/4.2migratedb/4.2.5createtask/4.2.5.1createtask.png?width=90pc)

3. Tại **Task identifier**, nhập ```WordPress-MySQL-to-Aurora```.
4. Tại **Replication instance**, chọn **mid-repinst-wp**.
5. Tại **Source database endpoint**, chọn **sourcewordpress**.
6. Tại **Target database endpoint**, chọn **targetwordpress**.
7. Tại **Migration Type**, chọn **Migrating existing data**.
![Migrate your database](../../../../images/4.migrateinfra/4.2migratedb/4.2.5createtask/4.2.5.2createtask.png?width=90pc)

8. Trong tính năng **Table mappings**, chọn **Wizard** tại **Editing mode**.
9. Nhấn **Add new selection data**.
10. Tại **Schema**, chọn **Enter a schema**.
11. Tại **Schema name**, chọn **%**.
12. Tại **Table name**, chọn **%**.
13. Tại **Action**, chọn **Include**.
![Migrate your database](../../../../images/4.migrateinfra/4.2migratedb/4.2.5createtask/4.2.5.3createtask.png?width=90pc)

14. Sau đó, nhấn **Create task**.
![Migrate your database](../../../../images/4.migrateinfra/4.2migratedb/4.2.5createtask/4.2.5.4createtask.png?width=90pc)

15. Hiện tại, bản sao của bạn từ máy chủ CSDL EC2 đến Aurora MySQL đang chạy và dữ liệu bắt đầu nhân bản.
![Migrate your database](../../../../images/4.migrateinfra/4.2migratedb/4.2.5createtask/4.2.5.5createtask.png?width=90pc)

### Giám sát tác vụ của bạn

Bây giờ tác vụ dịch chuyển của bạn đang hoạt động, chúng ta có thể giám sát chúng và đợi khi trạng thái **Load complete**.
![Migrate your database](../../../../images/4.migrateinfra/4.2migratedb/4.2.5createtask/4.2.5.6createtask.png?width=90pc)
