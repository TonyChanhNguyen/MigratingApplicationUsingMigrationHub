---
title : "Create IAM credential "
date : "`r Sys.Date()`"
weight : 5
chapter : false
pre : " <b> 2.5 </b> "
---

1. Go to [IAM User](https://us-east-1.console.aws.amazon.com/iam/home?region=us-west-2#/users).
2. Click to user name **ADSUser**.
3. Select **Security Credentials**.
4. Click on **Create Access Key**.
![Create Credential](/images/2.prerequires/2.5createcredential/2.5.1createcredential.png?width=90pc)

5. At **Use case** field, select **Command Line Interface (CLI)**.
6. Check box at **Confirmation**.
7. Then, click on **Next**.
![Create Credential](/images/2.prerequires/2.5createcredential/2.5.2createcredential.png?width=90pc)

8. Input the description ```Access key for FCJ workshop```.
9. Click on **Create access key**.
![Create Credential](/images/2.prerequires/2.5createcredential/2.5.3createcredential.png?width=90pc)

10. Download the .csv file and rename as **ADSUser.csv** as the information on this file will be used later.
![Create Credential](/images/2.prerequires/2.5createcredential/2.5.4createcredential.png?width=90pc)

 {{%notice warning%}}
Make sure that credential file was downloaded successfully.
{{%/notice%}}