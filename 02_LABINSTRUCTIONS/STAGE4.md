# Demo - Application Migration Service (MGN) - Launch Template

- Stage 1 Establish Private Connectivity Between the environments (VPC Peer)
- Stage 2 Replication Template
- Stage 3 Add Source Server
- Stage 4 Launch Template <= `YOU ARE HERE`
- Stage 5 Test & Cutover
- Stage 6 Cleanup

# Launch Template

Move to the MGN Console https://console.aws.amazon.com/mgn/home

In the menu select `Launch template` under `Settings` and click `Edit`

Under Default target subnet select AWSSNPublic

Under Additional security groups select AWSInstanceSG-

Click Save template

