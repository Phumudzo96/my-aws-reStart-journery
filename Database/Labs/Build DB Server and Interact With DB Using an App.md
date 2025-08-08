# Build DB Server and Interact With DB Using an App

## Objective
Launch a Multi-AZ Amazon RDS MySQL instance.

Configure security groups to allow communication between a web server and an RDS database.

Use a web application to interact with and persist data in the database.

## Steps Taken
✅ Created a Security Group for the RDS DB Instance

Name: DB Security Group

Rule: Allow inbound MySQL/Aurora traffic (port 3306) from the Web Security Group.

✅ Created a DB Subnet Group

Name: DB Subnet Group

Added Private Subnet 1 (10.0.1.0/24) and Private Subnet 2 (10.0.3.0/24)

Ensured subnets were in two different Availability Zones.

✅ Launched a Multi-AZ Amazon RDS Instance

Engine: MySQL

Instance Class: db.t3.medium

Storage: General Purpose SSD

VPC: Lab VPC

Security Group: DB Security Group

Initial DB Name: lab

Master Username: main

Password: lab-password

Disabled automated backups to speed up deployment.

✅ Configured Web Application to Use RDS DB

Opened the web app in a browser using WebServer public IP.

Entered RDS connection details (endpoint, DB name, username, password).

Submitted configuration to connect the app to the database.

Verified functionality by adding, editing, and removing contacts in the Address Book

## Challenges
❌ Initially had no inbound rule for the database to accept traffic from the web server.

✅ Solved by creating DB Security Group with a MySQL/Aurora rule allowing inbound traffic from the Web Security Group.

## Screenshot
<img width="1920" height="873" alt="Screenshot (603)" src="https://github.com/user-attachments/assets/6b54c7a3-c0c4-4e9c-b822-dd4538a6b7c3" />
<img width="1920" height="888" alt="Screenshot (604)" src="https://github.com/user-attachments/assets/29d23582-c91b-40a9-88bb-b774bc561e38" />
<img width="1920" height="875" alt="Screenshot (605)" src="https://github.com/user-attachments/assets/e4560da1-bcf4-419c-8869-74a7cea983cf" />
<img width="1920" height="886" alt="Screenshot (606)" src="https://github.com/user-attachments/assets/b0c425cd-bdc3-4f01-90c8-f401193c19b8" />
<img width="1920" height="880" alt="Screenshot (607)" src="https://github.com/user-attachments/assets/7c027493-cf5d-45c5-bf37-e41128f7bdb3" />

## Takeaways
✅ Multi-AZ RDS increases availability and durability by replicating data to a standby in another AZ.

✅ Security Groups act like firewalls—ensure you allow the correct source and port for your DB.

✅ Web applications can easily integrate with AWS-managed databases without needing to handle database maintenance manually.
