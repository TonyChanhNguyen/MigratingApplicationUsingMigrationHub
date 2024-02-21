---
title : "Giới thiệu"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---

### Nội dung
1. [Giới thiệu](../1-introduce)
2. [Các bước chuẩn bị](../2-prerequiste/)
    + 2.1 [Tạo Key Pair](../2-prerequiste/2.1-createkeypair/)
    + 2.2 [Triển khai mẫu CloudFormation](../2-prerequiste/2.2-lauchcloudformationtemplate/)
    + 2.3 [Kết nối Bastion Host](../2-prerequiste/2.3-connecttobastionhost/)
    + 2.4 [Khám phá môi trường](../2-prerequiste/2.4-exploreenvironment/)
    + 2.5 [Tạo chứng thực IAM](../2-prerequiste/2.5-createiamcredential/)
3. [Khám phá hạ tầng hiện có](../3-discoveryexistinginfrastructure/)
    + 3.1 [Kích hoạt tích hợp Athena](../3-discoveryexistinginfrastructure/3.1-enableathenaintegration/)
    + 3.2 [Tải ADS Agent cho VMs](../3-discoveryexistinginfrastructure/3.2-installadsagenttovms/)
    + 3.3 [Duyệt qua dữ liệu được khám phá](../3-discoveryexistinginfrastructure/3.3-browsediscovereddata/)
    + 3.4 [Trực quan kết nối mạng](../3-discoveryexistinginfrastructure/3.4-viewingnetworkconnections/)
    + 3.5 [Bảng khuyến nghị máy chủ EC2 ](../3-discoveryexistinginfrastructure/3.5-ec2instancerecommendations/)
    + 3.6 [Khám phá dữ liệu sử dụng Athena](../3-discoveryexistinginfrastructure/3.6-exploredatausingathena/)
4. [Dịch chuyển hạ tầng](../4-migratinginfrastructure/)
    + 4.1 [Dịch chuyển ứng dụng của bạn](../4-migratinginfrastructure/4.1-migratingyourapplication/)
        + 4.1.1 [Cấu hình dịch vụ AWS MGN](../4-migratinginfrastructure/4.1-migratingyourapplication/4.1.1-configureawsmgnservice/)
        + 4.1.2 [Cấu hình target template mặc định](../4-migratinginfrastructure/4.1-migratingyourapplication/4.1.2-configuredefaulttargettemplates/)
        + 4.1.3 [Tạo IAM user cho AWS replication agent](../4-migratinginfrastructure/4.1-migratingyourapplication/4.1.3-createawsreplicationagentiamuser/)
        + 4.1.4 [Tải AWS replication agent](../4-migratinginfrastructure/4.1-migratingyourapplication/4.1.4-installawsreplicationagent/)
        + 4.1.5 [AWS MGN migration lifecycle](../4-migratinginfrastructure/4.1-migratingyourapplication/4.1.5-awsmgnmigrationlifecycle/)
        + 4.1.6 [Triển khai máy chủ kiểm thử](../4-migratinginfrastructure/4.1-migratingyourapplication/4.1.6-launchtestinstance/)
        + 4.1.7 [Tắt môi trường nguồn](../4-migratinginfrastructure/4.1-migratingyourapplication/4.1.7-shutdownsourceenvironment/)
        + 4.1.8 [Triển khai máy chủ chuyển đổi](../4-migratinginfrastructure/4.1-migratingyourapplication/4.1.8-launchcutoverinstance/)
        + 4.1.9 [Cập nhật DNS và xác nhận các ứng dụng](../4-migratinginfrastructure/4.1-migratingyourapplication/4.1.9-updatednsandvalidatetheapplications/)
        + 4.1.10 [Hoàn thiện chuyển đổi và lưu trữ máy chủ](../4-migratinginfrastructure/4.1-migratingyourapplication/4.1.10-finalizecutoverandarchiveservers/)
    + 4.2 [Dịch chuyển cơ sở dữ liệu của bạn](../4-migratinginfrastructure/4.2-migratingyourdatabase/)
        + 4.2.1 [Tạo cơ sở dữ liệu target Aurora cuối cùng](../4-migratinginfrastructure/4.2-migratingyourdatabase/4.2.1-createaurorafinaltargetdatabases)
        + 4.2.2 [Tạo replication subnet groups](../4-migratinginfrastructure/4.2-migratingyourdatabase/4.2.2-createreplicaitonsubnetgroups/)
        + 4.2.3 [Tạo một replication instance](../4-migratinginfrastructure/4.2-migratingyourdatabase/4.2.3-createareplicationinstance)
        + 4.2.4 [Chỉ định endpoint của source và target](../4-migratinginfrastructure/4.2-migratingyourdatabase/4.2.4-specifysourceandtargetendpoints)
        + 4.2.5 [Tạo và giám sát các tác vụ](../4-migratinginfrastructure/4.2-migratingyourdatabase/4.2.5-createandmonitorthetasks/)
        + 4.2.6 [Tắt máy chủ nguồn và cập nhật DNS](../4-migratinginfrastructure/4.2-migratingyourdatabase/4.2.6-shutdownsourceserverandupdatedns/)
5. [Dọn dẹp tài nguyên](../5-cleanup/)