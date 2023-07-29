# Demo - Application Migration Service (MGN) - Cleanup

- Stage 1 Replication Template 
- Stage 2 Add Source Server
- Stage 3 Launch Template
- Stage 4 Test & Cutover
- Stage 5 Cleanup <= `YOU ARE HERE`

# Delete source server

Head to the MGN dashboard: [https://console.aws.amazon.com/mgn/home](https://console.aws.amazon.com/mgn/home) 

In the menu select `Source servers` and click on our source server 

Click <kbd>Actions</kbd>, <kbd>Disconnect from service</kbd> and then <kbd>Ok</kbd>

Click <kbd>Actions</kbd>, <kbd>Mark as archived</kbd> and then <kbd>Archive</kbd>

# Terminate EC2 Instances

Head to the EC2 dashboard: [https://console.aws.amazon.com/ec2/home](https://console.aws.amazon.com/ec2/home)

In the menu select `Instances` and terminate the migrated server `ip-PRIVATEIP.ec2.internal`

Wait till they are terminated

In the menu select `Volumes` under `Elastic Block Store` and delete the volumes created by AWS Application Migration Service (including the `ip-PRIVATEIP.ec2.internal` volume)

In the menu select `Snapshots` under `Elastic Block Store` and delete the snapshots created by AWS Application Migration Service

In the menu select `Security Groups` under `Network & Security` and delete the security groups created by AWS Application Migration Service
# MGN User

Head to the IAM dashboard: [https://console.aws.amazon.com/iam/home](https://console.aws.amazon.com/iam/home)

In the menu select `Users` under `Access management`

Select the `MGNUser` and click <kbd>Delete</kbd>, confirm that you want to delete by typing the name and click <kbd>Delete</kbd> again

# Delete Cloudformation Stack

Head to the Cloudformation dashboard: [https://console.aws.amazon.com/cloudformation/home](https://console.aws.amazon.com/cloudformation/home)

Click on your one-click deployment stack and delete it