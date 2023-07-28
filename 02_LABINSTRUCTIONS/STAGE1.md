# Demo - Application Migration Service (MGN) - Replication Template

- Stage 1 Replication Template <= `YOU ARE HERE`
- Stage 2 Add Source Server
- Stage 3 Launch Template
- Stage 4 Test & Cutover
- Stage 5 Cleanup

# Replication Template

Move to the MGN Console https://console.aws.amazon.com/mgn/home

In the menu select `Replication Template` under `Settings`

Click `Edit`

Under `Staging area subnet` select the `AWSSNPublic` subnet

Under `Replication Server instance type` select `t2.small`

Under `Data routing and throttling` select `Create public IP`

Click `Save template`
