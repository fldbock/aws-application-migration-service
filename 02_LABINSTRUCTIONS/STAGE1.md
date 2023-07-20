# Demo - Application Migration Service (MGN) - Establish Private Connectivity Between the environments (VPC Peer)

- Stage 1 Establish Private Connectivity Between the environments (VPC Peer) <= `YOU ARE HERE`
- Stage 2 Replication Template
- Stage 3 Add Source Server
- Stage 4 Launch Template
- Stage 5 Test & Cutover
- Stage 6 Cleanup

# STAGE 1A - Create a VPC peer between On-Premises and AWS

Move to the VPC Console https://console.aws.amazon.com/vpc/home

Click on `Peering Connections` under `Virtual Private Cloud`

Click `Create Peering Connection`
for `Peering connection name tag` choose `ON-PREMISES-TO-AWS`
for `VPC (Requester)` choose `onpremVPC`
for `VPC (Accepter)` choose `awsVPC`
Scroll down and click `Create Peering Connection`
...then click `Actions` and then `Accept Request`
Click `Accept Request`


# STAGE 1B - Create Routes on the On-premises side
Move to the route tabes console https://console.aws.amazon.com/vpc/home?#RouteTables:sort=routeTableId
Locate the `ONPREM-RT-PUBLIC` route table and select it using the checkbox.
Click on the `Routes` Tab.
You're going to add a route pointing at the AWS side networking, using the VPC Peer.
Click `Edit Routes`
Click `Add Route`
For Destination enter `10.0.1.0/24`
Click the `Target` dropdown & click `Peering Connection` and select the `ON-PREMISES-TO-AWS` then click `Save Changes`
The Onpremises network can now route to the AWS Network, but as data transfer requires bi-directional traffic flow, you need to do the same at the other side.

# STAGE 1C - Create Routes on the AWS side
Move to the route tabes console https://console.aws.amazon.com/vpc/home#RouteTables:sort=routeTableId
Locate the `AWS-RT-PUBLIC` route table and select it using the checkbox.
Click on the `Routes` Tab.
You're going to add a route pointing at the AWS side networking, using the VPC Peer.
Click `Edit Routes`
Click `Add Route`
For Destination enter `192.168.10.0/24`
Click the `Target` dropdown & click `Peering Connection` and select the `ON-PREMISES-TO-AWS` then click `Save Changes`

# STAGE 1 - FINISH   

At this point you have created the peering connection between the VPCs and the gateway objects within each VPC.
you have also configured routing from ONPremises -> AWS and vice-versa.


