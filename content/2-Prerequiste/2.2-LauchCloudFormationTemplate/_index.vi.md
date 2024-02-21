---
title : "Triển khai mẫu CloudFormation"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 2.2 </b> "
---

1. Đi đến [CloudFormaiton](https://us-west-2.console.aws.amazon.com/cloudformation/home?region=us-west-2).
2. Nhấn **Create stacks**.
![Launch CloudFormation](../../../images/2.prerequires/2.2launchcloudformation/2.2.1launchcloudformation.png?width=90pc)

3. Tại mục **Prepare template**, chọn **Template is ready**.
4. Tại mục **Template source**, chọn **Amazon S3 URL**.
5. Tại mục **Amazon S3 URL**, nhập URL ```https://ws-assets-prod-iad-r-pdx-f3b3f9f1a7d6a3d0.s3.us-west-2.amazonaws.com/a033522c-f256-40f9-9ecb-5b76a71589bc/self-paced/MID.yaml ```.
6. Sau đó, nhấn **Next**.
![Launch CloudFormation](../../../images/2.prerequires/2.2launchcloudformation/2.2.2launchcloudformation.png?width=80pc)

7. Tại mục **Stack name**, nhập ```FCJ-MigrationHub-Workshop```.
8. Tại mục **RootPassword**, nhập ```12345678```.
9. Tại mục **EC2KeyPairPublicKey**, nhập public key pair mà bạn vừa tạo ở bước 13 của [Create Key pair](../2.1-createkeypair/).
![Launch CloudFormation](../../../images/2.prerequires/2.2launchcloudformation/2.2.3launchcloudformation.png?width=90pc)

10. Tại mục **LaunchWindows**, chọn **TRUE** và giữ mặc định ở các mục còn lại.
11. Sau đó, nhấn **Next**.
![Launch CloudFormation](../../../images/2.prerequires/2.2launchcloudformation/2.2.4launchcloudformation.png?width=90pc)

12. Tại trang **Configure stack options**, giữ mặc định tất cả và nhấn **Next**.
13. Tại trang **Review**, tích cả hai lựa chọn:
    + I acknowledge that AWS CloudFormation might create IAM resources with custom names, and
    + I acknowledge that AWS CloudFormation might require the following capability: CAPABILITY_AUTO_EXPAND
14. Nhấn **Submit** để khởi động triển khai CloudFormation stack.
![Launch CloudFormation](../../../images/2.prerequires/2.2launchcloudformation/2.2.5launchcloudformation.png?width=90pc)

15. Kiểm tra kết quả, stack đang triển khai
![Launch CloudFormation](../../../images/2.prerequires/2.2launchcloudformation/2.2.6launchcloudformation.png?width=90pc)

 {{%notice info%}}
 Sẽ mất khoảng 20 phút để stack được tạo thành công
{{%/notice%}}

16. Sau khi stack được tạo, kiểm tra và đảm bảo rằng có 7 nested stack được tạo cùng.
    + FCJ-MigrationHub-Workshop-SOURCEBASTION-XXXXXXXXXXXXX
    + FCJ-MigrationHub-Workshop-SOURCEWINDOWS-XXXXXXXXXXXX
    + FCJ-MigrationHub-Workshop-SOURCEOFBIZ-XXXXXXXXXXXX
    + FCJ-MigrationHub-Workshop-SOURCEWORDPRESS-XXXXXXXXXXXX
    + FCJ-MigrationHub-Workshop-SOURCENETWORK-XXXXXXXXXXXXX
    + FCJ-MigrationHub-Workshop-ADSIAM-XXXXXXXXXXXX
    + FCJ-MigrationHub-Workshop-Tracker-XXXXXXXXXXXXX

![Launch CloudFormation](../../../images/2.prerequires/2.2launchcloudformation/2.2.7launchcloudformation.png?width=90pc)
