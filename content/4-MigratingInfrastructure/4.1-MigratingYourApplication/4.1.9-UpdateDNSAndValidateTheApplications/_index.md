---
title : "Update DNS and validate the applications"
date : "`r Sys.Date()`"
weight : 9
chapter : false
pre : " <b> 4.1.9 </b> "
---

Now that the OFbiz source servers are shutdown, it's time to update the DNS records to reflect the new servers that have just been migrated. In this lab we use an instance running a version of Unix bind/named as the DNS resolver.

1. Go to [EC2 instances](https://us-west-2.console.aws.amazon.com/ec2/home?region=us-west-2#Instances:instanceState=running).
2. Filter ```ofbiz```, and **Instance state** is **running**.
3. Save **Private IPv4 addresses** of two servers **ofbiz-db.onpremsim.env** and **ofbiz-web.onpremsim.env**.
![Migrating your application](../../../images/4.migrateinfra/4.1migrateapp/4.1.9dns/4.1.9.1dns.png?width=90pc)

4. From the Bastion host, use Putty to connect to the new IP address.
+ Log in: user
+ Password: 12345678
![Migrating your application](../../../images/4.migrateinfra/4.1migrateapp/4.1.9dns/4.1.9.2dns.png?width=90pc)

5. Run the following command to update the DNS record:
```
ADDR=`hostname -I`
HOST=`hostname`
sudo touch /tmp/nsupdate.txt
sudo chmod 666 /tmp/nsupdate.txt
echo "server dns.onpremsim.env" > /tmp/nsupdate.txt
echo "update delete $HOST A" >> /tmp/nsupdate.txt
echo "update add $HOST 86400 A $ADDR" >> /tmp/nsupdate.txt
echo "update delete $HOST PTR" >> /tmp/nsupdate.txt
echo "update add $HOST 86400 PTR $ADDR" >> /tmp/nsupdate.txt
echo "send" >> /tmp/nsupdate.txt
sudo nsupdate /tmp/nsupdate.txt
```

![Migrating your application](../../../images/4.migrateinfra/4.1migrateapp/4.1.9dns/4.1.9.3dns.png?width=90pc)

6. Repeat the DNS update process with remaining server.

![Migrating your application](../../../images/4.migrateinfra/4.1migrateapp/4.1.9dns/4.1.9.4dns.png?width=90pc)

7. Using **Windows PowerShell** of Bastion Host to run those command for performing testing new DNS of servers. 
```
nslookup ofbiz-web.onpremsim.env
nslookup ofbiz-db.onpremsim.env
```
![Migrating your application](../../../images/4.migrateinfra/4.1migrateapp/4.1.9dns/4.1.9.5dns.png?width=90pc)

You can see, returned IP Address is Private IP Address of each instance.

8. Now you can test the OfBiz that have just been migrated. They are running in AWS now. Open the following URL using Chrome.
+ URL: https://ofbiz-web.onpremsim.env:8443/accounting 
+ App username: admin
+ App password: ofbiz

![Migrating your application](../../../images/4.migrateinfra/4.1migrateapp/4.1.9dns/4.1.9.6dns.png?width=90pc)