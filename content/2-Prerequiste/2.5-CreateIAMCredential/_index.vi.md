---
title : "Tạo chứng thực IAM "
date :  "`r Sys.Date()`" 
weight : 5
chapter : false
pre : " <b> 2.5 </b> "
---

1. Đi đến [IAM User](https://us-east-1.console.aws.amazon.com/iam/home?region=us-west-2#/users).
2. Nhấn vào **ADSUser**.
3. Chọn **Security Credentials**.
4. Nhấn **Create Access Key**.
![Create Credential](/images/2.prerequires/2.5createcredential/2.5.1createcredential.png?width=90pc)

5. Tại mục **Use case**, chọn **Command Line Interface (CLI)**.
6. Tích chọn tại **Confirmation**.
7. Sau đó, nhấn **Next**.
![Create Credential](/images/2.prerequires/2.5createcredential/2.5.2createcredential.png?width=90pc)

8. Nhập mô tả ```Access key for FCJ workshop```.
9. Nhấn **Create access key**.
![Create Credential](/images/2.prerequires/2.5createcredential/2.5.3createcredential.png?width=90pc)

10. Tải tệp .csv và đổi tên thành **ADSUser.csv** vì thông tin trong tệp này sẽ được sử dụng sau.
![Create Credential](/images/2.prerequires/2.5createcredential/2.5.4createcredential.png?width=90pc)

 {{%notice warning%}}
Đảm bảo rằng tệp chứng thực của bạn đã được tải xuống thành công.
{{%/notice%}}
