# Demo - Application Migration Service (MGN) - Test & Cutover 

![Architecture](https://github.com/fldbock/aws-application-migration-service/blob/main/02_LABINSTRUCTIONS/STAGE4.png)

- Stage 1 Replication Template
- Stage 2 Add Source Server
- Stage 3 Launch Template
- Stage 4 Test & Cutover <= `YOU ARE HERE`
- Stage 5 Cleanup

# Lifecycle: Not ready

Head to the MGN dashboard: [https://console.aws.amazon.com/mgn/home](https://console.aws.amazon.com/mgn/home) 

In the menu select `Source servers` and click on your source server

In the `Migration dashboard` tab you will see that the service is completing the `Replication initiation steps`, wait until the lifecycle stage becomes `Ready for testing`

# Lifecycle: Ready for testing/Test in progress

Head to the MGN dashboard: [https://console.aws.amazon.com/mgn/home](https://console.aws.amazon.com/mgn/home) 

In the menu select `Source servers` and click on your source server

Click <kbd>Test and cutover</kbd>, <kbd>Launch test instances</kbd> and then <kbd>Launch</kbd> 

Head to the EC2 dashboard: [https://console.aws.amazon.com/ec2/home](https://console.aws.amazon.com/ec2/home)
 
In the menu select `Instances`

First a conversion server will be launched, then the test server will launch. Wait until the test server is active and has passed both status checks

Select the `testserver` and click <kbd>Connect</kbd>

Select `EC2 Instance Connect`

Under `User name` type `ec2-user` instead of `root`

Click <kbd>Connect</kbd>

Type `ls` and press enter

You should see the `secretfile.txt`, which verifies we replicated the linux server

Go back to the source server dashboard and click <kbd>Test and cutover</kbd>, <kbd>Mark as “Ready for cutover“</kbd> and then <kbd>Continue“</kbd>

# Lifecycle: Ready for Cutover/Cutover

Head to the MGN dashboard: [https://console.aws.amazon.com/mgn/home](https://console.aws.amazon.com/mgn/home) 

In the menu select `Source servers` and click on your source server

Click <kbd>Test and cutover</kbd>, <kbd>Launch cutover instances</kbd> and then <kbd>Launch</kbd> 

Head to the EC2 dashboard: [https://console.aws.amazon.com/ec2/home](https://console.aws.amazon.com/ec2/home)
 
In the menu select `Instances`

First a conversion server will be launched, then the cutover server will launch. Wait until the cutover server is active and has passed both status checks

Select the `cutoverserver` and click <kbd>Connect</kbd>

Select `EC2 Instance Connect`

Under `User name` type `ec2-user` instead of `root`

Click <kbd>Connect</kbd>

Type `ls` and press enter

You should see the `secretfile.txt`, which verifies that the cutover was performed correctly

# Lifecycle: Cutover complete

Head to the MGN dashboard: [https://console.aws.amazon.com/mgn/home](https://console.aws.amazon.com/mgn/home) 

In the menu select `Source servers` and click on your source server

Click <kbd>Test and cutover</kbd>, <kbd>Finalize cutover</kbd> and then <kbd>Finalize</kbd>

We now have successfully replicated our linux server for on premisses to the cloud. In the next stage we will delete all the resources we have created.