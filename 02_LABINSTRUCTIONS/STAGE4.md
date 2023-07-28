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

# Lifecycle: Ready for testing/Test in progress

Click `Test and cutover`, `Launch test instance` and then `Launch` 

Wait till the test instance is launched and passed the 2 status checks, first there will be a conversion server

Select the testserver, click `connect`

EC2 Instance connect

Under `User name` Type `ec2-user` instead of `root`

Type `ls`

You should see the secretfile.txt, which verifies we replicated the linux server

Go back to the source server dashboard and click Test and cutover and then Mark as “Ready for cutover“

# Lifecycle: Ready for Cutover/Cutover

Click `Test and cutover`, `Launch cutover instance` and then `Launch` 

Wait till the test instance is launched and passed the 2 status checks, first there will be a conversion server

Select the cutoverserver, click `connect`

EC2 Instance connect

Under `User name` Type `ec2-user` instead of `root`

Type `ls`

# Lifecycle: Cutover complete

Click `Test and cutover`, `Finalize cutover` and then `something else`