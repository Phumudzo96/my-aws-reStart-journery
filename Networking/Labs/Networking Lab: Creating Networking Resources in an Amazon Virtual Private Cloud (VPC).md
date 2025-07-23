# Networking Lab: Creating Networking Resources in an Amazon Virtual Private Cloud (VPC)
## Objective
Learn how to:

Create a VPC, Subnet, Internet Gateway, Route Table, NACL, Security Group, and EC2 instance within AWS.

Establish network connectivity and validate it using ping to confirm the VPC can reach the internet.

## Scenario
You are a Cloud Support Engineer at AWS assisting a startup customer (Brock) who cannot ping outside his VPC. Your goal is to configure the VPC architecture correctly to enable internet connectivity.

## Steps Taken
✅ Created a VPC

CIDR: 192.168.0.0/18

Name: Test VPC

✅ Created Public Subnet

CIDR: 192.168.1.0/26

Name: Public Subnet

Auto-assign public IP enabled.

✅ Created and attached an Internet Gateway

Name: IGW Test VPC

Attached it to Test VPC.

✅ Created a Route Table

Name: Public Route Table

Added route:

Destination: 0.0.0.0/0

Target: Internet Gateway (IGW Test VPC)

Associated the route table with Public Subnet.

✅ Created a Network ACL (NACL)

Name: Public Subnet NACL

Inbound: Allow all traffic (0.0.0.0/0)

Outbound: Allow all traffic (0.0.0.0/0)

Associated with Public Subnet.

✅ Created a Security Group

Name: Public Security Group

Description: Allows public access

Inbound Rules:

SSH (TCP 22) from 0.0.0.0/0

HTTP (TCP 80) from 0.0.0.0/0

HTTPS (TCP 443) from 0.0.0.0/0

Outbound Rules:

All traffic allowed (0.0.0.0/0)

✅ Launched an EC2 Instance

AMI: Amazon Linux 2023

Instance Type: t3.micro

Key Pair: vockey

Subnet: Public Subnet

Security Group: Public Security Group

Enabled Auto-assign Public IP.

✅ Validated connectivity

SSH’d into the instance using:

bash
Copy
Edit
ssh -i vockey.pem ec2-user@<public-ip>
Verified internet connectivity using:

bash
Copy
Edit
ping google.com
Successfully received responses, confirming network connectivity from the VPC.

## Challenges
❌ Initially forgot to associate the Route Table with the subnet, resulting in no internet connectivity.  
✅ Resolved by associating the Public Subnet with the Public Route Table and confirming the IGW route.

## Screenshot
<img width="1920" height="876" alt="Screenshot (715)" src="https://github.com/user-attachments/assets/8d2183e1-9e04-451d-b8e0-fb07fb0da3db" />
<img width="1920" height="880" alt="Screenshot (716)" src="https://github.com/user-attachments/assets/fad3bdfd-9164-431d-88f1-d6959388387c" />
<img width="1920" height="873" alt="Screenshot (717)" src="https://github.com/user-attachments/assets/8aa6bff3-d487-4960-829d-83b90632ac33" />
<img width="1920" height="873" alt="Screenshot (718)" src="https://github.com/user-attachments/assets/35cc2336-b1ef-4071-89d1-559caff12179" />
<img width="1920" height="869" alt="Screenshot (719)" src="https://github.com/user-attachments/assets/2ceb7d54-6f0e-466a-a19b-8522b5d92124" />
<img width="1920" height="873" alt="Screenshot (720)" src="https://github.com/user-attachments/assets/70effcae-3c31-41e8-912e-ccdb5806df8f" />
<img width="1920" height="862" alt="Screenshot (721)" src="https://github.com/user-attachments/assets/181c9660-98b9-4c4d-8f72-627a43f93a9a" />
<img width="1920" height="876" alt="Screenshot (722)" src="https://github.com/user-attachments/assets/6083e80b-823b-4d42-98ec-95032c608909" />
<img width="1920" height="880" alt="Screenshot (723)" src="https://github.com/user-attachments/assets/b197a8e6-be85-4823-9462-cf388790a42d" />
<img width="1920" height="876" alt="Screenshot (724)" src="https://github.com/user-attachments/assets/3be9b6d3-5d00-4bf5-843f-2e1691608088" />
<img width="1916" height="876" alt="Screenshot (725)" src="https://github.com/user-attachments/assets/725b2a49-5eb1-4117-be65-2159eb9fb400" />


## Takeaways
✅ A functional VPC requires:

Properly configured subnets with public IP assignment.

An Internet Gateway attached and correctly routed (0.0.0.0/0) in the route table.

Security Groups and NACLs that allow required inbound/outbound traffic.

Associating route tables to the correct subnets is critical for connectivity.

✅ VPC networking workflow:

Create VPC → Subnet → IGW → Route Table → NACL → Security Group → EC2.

Always test connectivity using ping or curl to validate correct internet routing.

✅ This lab reinforces practical AWS networking skills essential for troubleshooting customer connectivity issues as a Cloud Support Engineer.

## Architectural diagram

<img width="813" height="431" alt="Networking Resources in an Amazon Virtual Private Cloud" src="https://github.com/user-attachments/assets/eb3f5aa5-ec3a-46b8-bf89-abf2dbb27a3a" />
