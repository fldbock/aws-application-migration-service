# Demo - Application Migration Service (MGN) - Test & Cutover 

- Stage 1 Replication Template
- Stage 2 Add Source Server
- Stage 3 Launch Template
- Stage 4 Test & Cutover <= `YOU ARE HERE`
- Stage 5 Cleanup

# Lifecycle: Not ready

Move to the MGN Console https://console.aws.amazon.com/mgn/home

In the menu select `Source servers` and click on your source server

In the `Migration dashboard` tab you will see that the sevice is completing `Replication initiation steps` wait till the lifecycle stage becomes `Ready for testing`

# Lifecycle: Test in progress

Click `Test and cutover`, `Launch` and then `Launch test instance`

Wait till the test instance is launched and passed the 2 status checks, first there will be a conversion server

Select the testserver, click `connect`

EC2 Instance connect

Type `ec2-user` instead of `root`

Type `ls`

# Lifecycle: Cutover

Click `Test and cutover`, `Launch` and then `Launch cutover instance`

Wait till the cutover instance is launched and passed the 2 status checks

Select the cutoverserver, click `connect`

EC2 Instance connect

Type `ec2-user` instead of `root`

Type `ls`