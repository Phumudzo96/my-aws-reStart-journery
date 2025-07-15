# Lab: Configuring a VPC
Objective
Learn how to build a secure, scalable AWS network by creating a VPC with public and private subnets, routing, and a NAT gateway, and connecting to instances via a bastion host.

## Steps Taken
Logged into AWS Console.

Created a VPC (10.0.0.0/16).

Created a public subnet (10.0.0.0/24) and enabled auto-assign public IP.

Created a private subnet (10.0.2.0/23) for isolated resources.

Created and attached an Internet Gateway to the VPC.

Configured route tables:

Public route table with 0.0.0.0/0 routed to Internet Gateway.

Associated the public route table with the public subnet.

Launched a bastion EC2 instance in the public subnet for SSH access.

Created a NAT Gateway in the public subnet with Elastic IP.

Updated the private route table to route 0.0.0.0/0 traffic to the NAT Gateway.

## Challenges
Misconfigured route table association, preventing internet access initially.
✅ Fixed by associating the correct route table with the correct subnet.

Initially forgot to enable auto-assign public IP in the public subnet.
✅ Fixed by editing subnet settings.

## Screenshot
(Optional – paste image if available)

## Takeaways
✅ VPCs provide isolated, customizable networking for AWS resources.
✅ Subnets control resource exposure: public for internet-facing, private for isolated workloads.
✅ Internet Gateways and NAT Gateways enable secure, controlled internet access.
✅ Route Tables direct traffic efficiently within and outside the VPC.
✅ Using a bastion host allows secure SSH into private instances without exposing them directly to the internet.
✅ Testing connectivity confirms the correct functioning of VPC, NAT, and security configurations.

## Architectural diagram

<img width="431" height="456" alt="Lab- Configuring a VPC drawio" src="https://github.com/user-attachments/assets/981cd8e6-057b-4f84-a244-99032258877b" />
