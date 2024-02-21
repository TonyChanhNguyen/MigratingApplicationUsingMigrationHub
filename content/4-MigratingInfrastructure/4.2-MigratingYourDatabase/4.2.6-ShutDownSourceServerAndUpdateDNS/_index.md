---
title : "Shutdown source server and upadte DNS "
date : "`r Sys.Date()`"
weight : 4.2.6
chapter : false
pre : " <b> 4.2.6 </b> "
---

Now that all databases have been migrated to Aurora, it's time to update the DNS information so the application server can connect to the related Aurora database server. Both apps are using a DNS entry as a connection hostname. In a real-world application migration, once you have completed all of your testing and are ready to fully transition your databases to Aurora, you should perform the shutdown of the source servers and update the DNS records properly to reflect the new database servers running in Aurora.

1. From Bastion Host, SSH to instance name **wordpress-db**.
2. Check the current database DNS record running following command from the putty terminal:
```
nslookup wordpress-db
```

3. Let's create a variable (ADDR) using the RDS endpoint. See again at step 25 of [Create Aurora final target database](../4.2.1-CreateAuroraFinalTargetDatabases/).
```
ADDR="<REPLACE THIS WITH WORDPRESS ENDPOINT>"
```
4. Then, run the following commands to update the DNS record:
```
HOST="wordpress-db.onpremsim.env"
sudo touch /tmp/nsupdate.txt
sudo chmod 666 /tmp/nsupdate.txt
echo "server dns.onpremsim.env" > /tmp/nsupdate.txt
echo "update delete $HOST A" >> /tmp/nsupdate.txt
echo "update delete $HOST PTR" >> /tmp/nsupdate.txt
echo "update add $HOST 86400 CNAME $ADDR." >> /tmp/nsupdate.txt
echo "send" >> /tmp/nsupdate.txt
sudo nsupdate /tmp/nsupdate.txt
```
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.6shutdown/4.2.6.1shutdown.png?width=90pc)

5. Verify the DNS name resolution again.
```
nslookup wordpress-db
```
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.6shutdown/4.2.6.2shutdown.png?width=90pc)

It was updated to a CNAME pointing to your Aurora database (compare the output with the previous step).

6. Shutdown the source database server.
```
sudo shutdown -h now
```
7. From the Bastion Host, test the application using Chrome web browser with this URL http://wordpress-web.onpremsim.env/.

#### This is the expected screen if the migration was successful:
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.6shutdown/4.2.6.3shutdown.png?width=80pc)

### Congratulations, you had migrated your enterprise servers into AWS successfully.