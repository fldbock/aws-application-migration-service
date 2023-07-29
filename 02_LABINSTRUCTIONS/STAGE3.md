# Demo - Application Migration Service (MGN) - Launch Template

- Stage 1 Replication Template
- Stage 2 Add Source Server
- Stage 3 Launch Template <= `YOU ARE HERE`
- Stage 4 Test & Cutover
- Stage 5 Cleanup 

# EC2 Launch Template

Head to the MGN dashboard: [https://console.aws.amazon.com/mgn/home](https://console.aws.amazon.com/mgn/home) 

Click on your source server, in the menu select `Launch settings`, under `EC2 Launch Template` click <kbd>Modify</kbd>

Pick a `Template version description`, I'll use `template-v1`

Select the `AWSSNPublic` subnet

Under `Additional security groups` select `AWSInstanceSG-`

Open `Advanced network configuration` and set the `Auto-assign public IP` to `enable`

Click <kbd>Create template version</kbd>

Select the `launch template` click on <kbd>actions</kbd> then click on <kbd>Set Default version</kbd> to set the default version to the latest version