# Demo - Application Migration Service (MGN) - Launch Template

- Stage 1 Replication Template
- Stage 2 Add Source Server
- Stage 3 Launch Template <= `YOU ARE HERE`
- Stage 4 Test & Cutover
- Stage 5 Cleanup 

# EC2 Launch Template

Head to the MGN dashboard: [https://console.aws.amazon.com/mgn/home](https://console.aws.amazon.com/mgn/home) 

Click on your source server, in the menu click on Launch settings, under EC2 Launch Template click Modify

Pick a `Template version description`, I'll use  `template-v1`

Select awssnpublic subnet

Under `Additional security groups` select `AWSInstanceSG-`

Open `Advanced network configuration` and set the `Auto-assign public IP` to `enable`

Click `Create template version`

Select the `launch template` click on `actions` then click on `Set Default version` to set the default version to the latest version