# **Build Your VPC and Launch a Web Server** 

---

**Objective**
Create a custom VPC with public and private subnets across two Availability Zones, configure security rules, and launch a web server EC2 instance into the VPC.

---

**Steps Taken**

1. Created a **VPC** (10.0.0.0/16) with 1 public and 1 private subnet, internet gateway, NAT gateway, and route tables.
2. Added **two additional subnets** in a second AZ (Public Subnet 2: 10.0.2.0/24, Private Subnet 2: 10.0.3.0/24).
3. Associated **Public Subnet 2** with the public route table and **Private Subnet 2** with the private route table.
4. Created a **Web Security Group** in the VPC allowing HTTP traffic from anywhere (port 80).
5. Launched **Web Server 1** (Amazon Linux 2, t3.micro) in Public Subnet 2 with the Web Security Group.
6. Added **user data script** to install Apache, PHP, MySQL, and deploy the lab web application.
7. Retrieved the **Public IPv4 DNS** of the instance and verified the web server page in a browser.

---

**Challenges**

* Initially forgot to enable **Auto-assign public IP** for the EC2 instance.

  * **Solution**: Edited network settings during launch to enable it.
* Had to wait for NAT gateway creation before subnets showed proper internet routing.

  * **Solution**: Paused until NAT gateway status was “Available” before testing connectivity.

---

**Screenshot**
<img width="1920" height="869" alt="Screenshot (828)" src="https://github.com/user-attachments/assets/abd246ad-4110-4ea2-bb2e-e39ad806cdd7" />
<img width="1920" height="873" alt="Screenshot (829)" src="https://github.com/user-attachments/assets/20220e95-a4c6-4633-82e0-4ffb7c1564f2" />
<img width="1920" height="873" alt="Screenshot (830)" src="https://github.com/user-attachments/assets/c2ad26e7-38c4-4a27-a576-c098dd2c9b7a" />
<img width="1920" height="880" alt="Screenshot (831)" src="https://github.com/user-attachments/assets/da7f5aed-d6bc-4d9f-916f-d2a098dff08d" />
<img width="1916" height="876" alt="Screenshot (832)" src="https://github.com/user-attachments/assets/c5390e8e-a92a-4449-b242-8e53b9f67156" />
<img width="1920" height="876" alt="Screenshot (833)" src="https://github.com/user-attachments/assets/2be8bbfe-b836-406f-acae-b4a27beaa53d" />
<img width="1916" height="873" alt="Screenshot (834)" src="https://github.com/user-attachments/assets/0dec8250-698f-42f5-b37e-7aac1f70252c" />
<img width="1920" height="876" alt="Screenshot (835)" src="https://github.com/user-attachments/assets/102b3100-913c-4e85-8919-f1660a637326" />
<img width="1920" height="886" alt="Screenshot (836)" src="https://github.com/user-attachments/assets/4cb6fbb5-10c9-47ec-9373-755bff72a4db" />
<img width="1920" height="873" alt="Screenshot (837)" src="https://github.com/user-attachments/assets/557f2c8d-18e4-45f4-bb1e-a6c328480182" />
<img width="1920" height="875" alt="Screenshot (838)" src="https://github.com/user-attachments/assets/7ee29550-d1f6-4eed-a79d-0886df57caaf" />


---

**Takeaways**

* A **VPC** provides complete control over your AWS network design.
* Public subnets require a **route to an internet gateway** to be reachable from the internet.
* Private subnets can access the internet via a **NAT gateway**, but cannot be accessed from outside.
* Security groups act as **instance-level firewalls**, and inbound rules must allow required traffic (HTTP in this case).
* User data scripts are useful for **automating server setup** during instance launch.
is summary — similar to AWS training diagrams. That would make it very presentation-friendly. Would you like me to do that?
