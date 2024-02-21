---
title : "Create Key Pair "
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 2.1 </b> "
---

In this step, we will create a public key pair to provide for CloudFormation template when launching Bastion Host .The private potion of the key will be used to decrypt Bastion Host password later on to connect to the Bastion host using either SSM Fleet Manager or RDP client.

1. Go to [Key Pair](https://us-west-2.console.aws.amazon.com/ec2/home?region=us-west-2#KeyPairs:) of region ***Oregon (us-west-2)***
2. Click **Create Key Pair**.
![Create Key Pair](../../images/2.prerequires/2.1createkeypair/2.1.1createkeypair.png?width=90pc)

3. At **Name** field, input ```FCJ-keypair```.
4. At **Key pair type**, select **RSA**.
5. At **Private key file format**, select **.pem**.
6. Then click on **Create key pair**.
![Create Key Pair](../../images/2.prerequires/2.1createkeypair/2.1.2.1createkeypair.png?width=90pc)

7. Check your key pair created successful.
![Create Key Pair](../../images/2.prerequires/2.1createkeypair/2.1.3createkeypair.png?width=90pc)

 {{%notice warning%}}
Make sure that your key pair file had been downloaded automatically.
{{%/notice%}}

8. Open **PuttyGen**. If you did not download **PuttyGen** yet, follow [here](https://www.puttygen.com/) for more information.
9. Click on **File**, then click on **Load Private Key**.
10. Select file **FCJ-keypair.pem** you had downloaded.

 {{%notice tip%}}
Choose **All file** to see **FCJ-keypair.pem**.
{{%/notice%}}

11. Keep blank at **Key comment**.
12. Copy public key.
![Create Key Pair](../../images/2.prerequires/2.1createkeypair/2.1.6createkeypair.png?width=30pc)
13. Save it for using later.

