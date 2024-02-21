---
title : "Migrating application using Migration Hub "
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 1. </b> "
---
# Migrating application using Migration Hub
### Overview
In this workshop we will perform discovery and migration of an emulated production environment running on a customer datacenter. The environment consists of 2 applications and 4 servers.

All the concepts applied in this migration exercise can also be applied to 10s, 100s or 1000s of server migrations.

![Lab architecture](images/architecture.png?width=80pc)

This workshop uses an emulated on-premise environment with AWS EC2 servers, configured in a way that mimics a customers' environment, with private and public networks, DNS server, pre-installed applications and a bastion host.

Now, we will discover and migrate the 4 servers from the on-premise emulated source environment to AWS.

### To move forward with this workshop, it is required that the participants are familiar with:
+ Connecting to a Microsoft Windows Server using Remote Desktop Protocol (RDP)
+ Connecting to Linux servers using Putty
+ Basic Linux Bash commands
+ Basic Windows PowerShell commands
+ AWS Console
+ Basic DNS and domain name resolution
+ The following AWS Services (EC2, CloudFormation)

### Materials needed:
+ A computer (Linux, Windows or Mac)
+ Internet connectivity with outbound access to RDP protocol (TCP port 3389).
+ A valid AWS Account


### By the end of this workshop, you will:
+ Understand how migration projects works
+ Discover servers and applications using AWS Application Discovery Service
+ Group servers as applications using AWS Migration Hub
+ Migrate servers with MGN
+ Migrate databases with AWS Database Migration Service

 {{%notice warning%}}
The estimated cost in AWS resources for this lab are between USD$10 to USD$15 for a ~8 Hour lab duration. Make sure you terminate the CloudFormation and delete all the created resources during this lab after it's completion.
{{%/notice%}}
