# Demo - Application Migration Service (MGN) - Replication Template

- Stage 1 Establish Private Connectivity Between the environments (VPC Peer)
- Stage 2 Replication Template <= `YOU ARE HERE`
- Stage 3 Add Source Server
- Stage 4 Launch Template
- Stage 5 Test & Cutover
- Stage 6 Cleanup

# Replication Template

Move to the MGN Console https://console.aws.amazon.com/mgn/home

In the menu select `Replication Template` under `Settings`

Click `Edit`

Under `Staging area subnet` select the `AWSSNPublic` subnet

Under `Replication Server instance type` select `t2.small`

Under `Data routing and throttling` select `Create public IP`

Click `Save template`
