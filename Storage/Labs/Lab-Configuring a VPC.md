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
<img width="1920" height="865" alt="Screenshot (608)" src="https://github.com/user-attachments/assets/282b6bca-8e5d-42f9-a93b-f5ef3c4eb9c2" />
<img width="1920" height="873" alt="Screenshot (609)" src="https://github.com/user-attachments/assets/1e98e371-30ae-4d7f-a1e5-50056c61c9d5" />
<img width="1920" height="880" alt="Screenshot (610)" src="https://github.com/user-attachments/assets/50d1584e-2381-42d3-890c-b6a5f145fd29" />
<img width="1920" height="876" alt="Screenshot (612)" src="https://github.com/user-attachments/assets/9d7dad88-25c8-4eb6-851f-4e6d302928d2" />
<img width="1920" height="876" alt="Screenshot (613)" src="https://github.com/user-attachments/assets/cdfb13b6-cefd-4c67-b60e-c7dd8949f66a" />
<img width="1920" height="886" alt="Screenshot (614)" src="https://github.com/user-attachments/assets/fddf207c-1322-483d-8b7f-0bdf26a078ce" />
<img width="1920" height="876" alt="Screenshot (615)" src="https://github.com/user-attachments/assets/5e5bb8b8-5ce4-44c5-bc43-9e175ebc75f8" />
<img width="1920" height="873" alt="Screenshot (616)" src="https://github.com/user-attachments/assets/c5ccdbe1-ae36-49d5-9901-444088c14d9e" />
<img width="1920" height="876" alt="Screenshot (617)" src="https://github.com/user-attachments/assets/ac0e9835-090b-4b1a-a824-0ff3c4826b43" />



## Takeaways
✅ VPCs provide isolated, customizable networking for AWS resources.

✅ Subnets control resource exposure: public for internet-facing, private for isolated workloads.

✅ Internet Gateways and NAT Gateways enable secure, controlled internet access.

✅ Route Tables direct traffic efficiently within and outside the VPC.

✅ Using a bastion host allows secure SSH into private instances without exposing them directly to the internet.

✅ Testing connectivity confirms the correct functioning of VPC, NAT, and security configurations.

## Architectural diagram

<img width="431" height="456" alt="Lab- Configuring a VPC drawio" src="https://github.com/user-attachments/assets/981cd8e6-057b-4f84-a244-99032258877b" />
