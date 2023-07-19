# Demo - Application Migration Service (MGN) - Add Source Server

- Stage 1 Establish Private Connectivity Between the environments (VPC Peer)
- Stage 2 Replication Template
- Stage 3 Add Source Server <= `YOU ARE HERE`
- Stage 4 Launch Template
- Stage 5 Test & Cutover
- Stage 6 Cleanup

# Create MGN USER

Move to the IAM Console https://console.aws.amazon.com/iam/home

In the menu select `Users` under `Access management` and click `Add users`

Pick a `User name`, I'll use `MGNUser`

Click `Next`

Under `Permission options select Attach policies directly` and select the `AWSApplicationMigrationAgentInstallationPolicy`

Click `Next` and `Create user`

Click on the user, go to the `Security credentials tab` and click `Create access key` under `Access keys`

For `Use case` select `Application running outside of AWS`

Click `Next` and `Create access key`

Click `Download .csv file` and then `Done` (don't delete this csv file because we need it for later)


# Add Source Server

Move to the MGN Console https://console.aws.amazon.com/mgn/home

In the menu select `Source servers` and click `Add server`

Under `Users`Select your operating system select `Users`Linux

Keep `Users`Replicate all disks selected

Under `Users`provide the required credentials fill in the credentials from the csv file you downloaded earlier

# Session manager

Head to the EC2 dashboard: [https://console.aws.amazon.com/ec2/home](https://console.aws.amazon.com/ec2/home)
 
Go to `Instances`, select the OnpremServer instance and click <kbd>Connect</kbd>

Select `Session manager` and click <kbd>Connect</kbd>

Type `sudo bash` and press enter
Type `cd` and press enter

Download the installer using this command:
```
wget -O ./aws-replication-installer-init https://aws-application-migration-service-us-east-1.s3.us-east-1.amazonaws.com/latest/linux/aws-replication-installer-init
```

Copy and input the command below into the command line on your source server
```
sudo chmod +x aws-replication-installer-init; ./aws-replication-installer-init --region REGION --aws-access-key-id ACCESSKEYID --aws-secret-access-key SECRETACCESSKEY --no-prompt
```

Wait for the AWS Replication Agent to finish downloading and installing
