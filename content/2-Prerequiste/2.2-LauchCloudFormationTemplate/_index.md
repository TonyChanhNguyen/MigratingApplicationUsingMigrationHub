---
title : "Launch CloudFormation template "
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 2.2 </b> "
---

1. Go to [CloudFormaiton](https://us-west-2.console.aws.amazon.com/cloudformation/home?region=us-west-2).
2. Click on **Create stacks**.
![Launch CloudFormation](../../images/2.prerequires/2.2launchcloudformation/2.2.1launchcloudformation.png?width=90pc)

3. At **Prepare template** field, select **Template is ready**.
4. At **Template source** field, select **Amazon S3 URL**.
5. At **Amazon S3 URL**, input URL ```https://ws-assets-prod-iad-r-pdx-f3b3f9f1a7d6a3d0.s3.us-west-2.amazonaws.com/a033522c-f256-40f9-9ecb-5b76a71589bc/self-paced/MID.yaml ```.
6. Then, click on **Next**.
![Launch CloudFormation](../../images/2.prerequires/2.2launchcloudformation/2.2.2launchcloudformation.png?width=80pc)

7. At **Stack name** field, input ```FCJ-MigrationHub-Workshop```.
8. At **RootPassword** field, input ```12345678```.
9. At **EC2KeyPairPublicKey** field, input the public key pair which you had generated at step 13 of [Create Key pair](../2.1-createkeypair/).
![Launch CloudFormation](../../images/2.prerequires/2.2launchcloudformation/2.2.3launchcloudformation.png?width=90pc)

10. At **LaunchWindows** field, select **TRUE** and keep default at another fields.
11. Then, click on **Next**.
![Launch CloudFormation](../../images/2.prerequires/2.2launchcloudformation/2.2.4launchcloudformation.png?width=90pc)

12. At **Configure stack options** interface, keep all at default and click **Next**.
13. At **Review** interface, check both options:
    + I acknowledge that AWS CloudFormation might create IAM resources with custom names, and
    + I acknowledge that AWS CloudFormation might require the following capability: CAPABILITY_AUTO_EXPAND
14. Click on **Submit** to launch stack deployment.
![Launch CloudFormation](../../images/2.prerequires/2.2launchcloudformation/2.2.5launchcloudformation.png?width=90pc)

15. Verify the result, stack is launching.
![Launch CloudFormation](../../images/2.prerequires/2.2launchcloudformation/2.2.6launchcloudformation.png?width=90pc)

 {{%notice info%}}
It will take you about 20 minutes for stack created successfully.
{{%/notice%}}

16. After stack is created, check and make sure there are 7 nested stack were created together.
    + FCJ-MigrationHub-Workshop-SOURCEBASTION-XXXXXXXXXXXXX
    + FCJ-MigrationHub-Workshop-SOURCEWINDOWS-XXXXXXXXXXXX
    + FCJ-MigrationHub-Workshop-SOURCEOFBIZ-XXXXXXXXXXXX
    + FCJ-MigrationHub-Workshop-SOURCEWORDPRESS-XXXXXXXXXXXX
    + FCJ-MigrationHub-Workshop-SOURCENETWORK-XXXXXXXXXXXXX
    + FCJ-MigrationHub-Workshop-ADSIAM-XXXXXXXXXXXX
    + FCJ-MigrationHub-Workshop-Tracker-XXXXXXXXXXXXX

![Launch CloudFormation](../../images/2.prerequires/2.2launchcloudformation/2.2.7launchcloudformation.png?width=90pc)