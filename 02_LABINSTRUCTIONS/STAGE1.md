# Demo - Application Migration Service (MGN) - Replication Template

![Architecture](https://github.com/fldbock/aws-application-migration-service/blob/main/02_LABINSTRUCTIONS/STAGE1.png)

- Stage 1 Replication Template <= `YOU ARE HERE`
- Stage 2 Add Source Server
- Stage 3 Launch Template
- Stage 4 Test & Cutover
- Stage 5 Cleanup

# Replication Template

Head to the MGN dashboard: [https://console.aws.amazon.com/mgn/home](https://console.aws.amazon.com/mgn/home) 

In the menu select `Replication Template` under `Settings`

Click <kbd>Edit</kbd>

Under `Staging area subnet` select the `AWSSNPublic` subnet

Under `Replication Server instance type` select `t2.small`

Under `Data routing and throttling` select `Create public IP`

Click <kbd>Save template</kbd>

We now have configured our replication template which will instruct how our source server will be replicated. In the next stage we will connect the source server (OnpremServer) to the MGN sevice by installing the aws replication agent on the source server.
