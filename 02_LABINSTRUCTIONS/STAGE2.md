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

Under `Staging area subnet` select the `sn-aws-private` subnet

Under `Replication Server instance type` select `t2.small`

Under `Data routing and throttling` select `Use private IP for data replication (VPN, DirectConnect, VPC peering, etc.)`

Click `Save template`

