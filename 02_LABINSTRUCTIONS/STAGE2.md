# Demo - Application Migration Service (MGN) - Add Source Server

- Stage 1 Replication Template
- Stage 2 Add Source Server <= `YOU ARE HERE`
- Stage 3 Launch Template
- Stage 4 Test & Cutover
- Stage 5 Cleanup

# Create MGNUser

Head to the IAM dashboard: [https://console.aws.amazon.com/iam/home](https://console.aws.amazon.com/iam/home)

In the menu select `Users` under `Access management` and click <kbd>Add users</kbd>

Pick a `User name`, I'll use `MGNUser`

Click <kbd>Next</kbd>

Under `Permission options`, select `Attach policies directly` and select the `AWSApplicationMigrationAgentInstallationPolicy` policy

Click <kbd>Next</kbd> and <kbd>Create user</kbd>

Click on the user, go to the `Security credentials tab` and select `Create access key` under `Access keys`

For the `Use case` select `Application running outside of AWS`

Click <kbd>Next</kbd> and <kbd>Create access key</kbd>

Click <kbd>Download .csv file</kbd> and then <kbd>Done</kbd> (don't delete this csv file because we need it for later)


# Add Source Server

Head to the MGN dashboard: [https://console.aws.amazon.com/mgn/home](https://console.aws.amazon.com/mgn/home) 

In the menu select `Source servers` and click <kbd>Add server</kbd>

Under `Select your operating system` select `Linux`

Keep `Replicate all disks` selected

Under `provide the required credentials` fill in the credentials from the csv file you downloaded earlier

# Aws-replication-installer

Head to the EC2 dashboard: [https://console.aws.amazon.com/ec2/home](https://console.aws.amazon.com/ec2/home)
 
Go to `Instances`, select the OnpremServer instance and click <kbd>Connect</kbd>

Select `EC2 Instance Connect` and click <kbd>Connect</kbd>

We will create a textfile so that we can later confirm that this server is replicated.
```
touch secretfile.txt
```

Download the installer using this command:
```
sudo wget -O ./aws-replication-installer-init https://aws-application-migration-service-us-east-1.s3.us-east-1.amazonaws.com/latest/linux/aws-replication-installer-init
```

Copy and input the command below into the command line on your source server, you'll have to fill in the `ACCESSKEYID` and `SECRETACCESSKEY` of the MGNUser we created earlier.
```
sudo chmod +x aws-replication-installer-init; sudo ./aws-replication-installer-init --region REGION --aws-access-key-id ACCESSKEYID --aws-secret-access-key SECRETACCESSKEY --no-prompt
```

Wait for the AWS Replication Agent to finish downloading and installing

We now have the source server (OnpremServer) connected to our MGN Dashboard and ready for replication. It will take around 20 minutes for the initial replication of our server, so in the next stage we will configure the launch template. 