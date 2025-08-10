# **Compute Lab: Launching an EC2 Instance**

### **Objective**

Learn how to launch, configure, monitor, resize, and terminate an Amazon EC2 instance with termination protection enabled.

---

### **Steps Taken**

1. **Launched EC2 Instance**

   * Service: **Amazon EC2**
   * AMI: **Amazon Linux 2023**
   * Instance Type: **t3.micro**
   * Network: **Lab VPC**
   * Security Group: Created **Web Server security group** (no SSH access).
   * Storage: **8 GiB EBS volume** (default).
   * Enabled **termination protection**.
   * Added **User Data script** to install Apache web server:

     ```bash
     #!/bin/bash
     yum -y install httpd
     systemctl enable httpd
     systemctl start httpd
     echo '<html><h1>Hello From Your Web Server!</h1></html>' > /var/www/html/index.html
     ```
   * Launched instance and verified **running state**.

2. **Monitored the Instance**

   * Verified **2/2 status checks passed**.
   * Viewed **CloudWatch metrics** (basic monitoring).
   * Captured **instance console screenshot**.

3. **Updated Security Group for HTTP Access**

   * Added inbound rule:

     ```
     Type: HTTP
     Protocol: TCP
     Port: 80
     Source: Anywhere-IPv4
     ```
   * Accessed public IPv4 address in browser → confirmed “Hello From Your Web Server!” page.

4. **Resized the Instance**

   * **Stopped instance**.
   * Changed type from `t3.micro` → `t3.small`.
   * Increased EBS volume size from **8 GiB → 10 GiB**.
   * **Started instance** and confirmed changes.

5. **Tested Termination Protection**

   * Attempted termination → blocked by termination protection.
   * Disabled termination protection.
   * Terminated instance.

---

### **Challenges**

* Initially forgot to open **port 80** in security group, blocking web access.
  **Solution:** Added HTTP inbound rule to security group.

---

### **Screenshot**

<img width="1920" height="885" alt="Screenshot (794)" src="https://github.com/user-attachments/assets/1265916a-3349-462a-a9f5-e83fc5d7ae85" />
<img width="1920" height="876" alt="Screenshot (795)" src="https://github.com/user-attachments/assets/35e740e7-9af7-4b11-81e5-12cef5f426c5" />
<img width="1920" height="873" alt="Screenshot (796)" src="https://github.com/user-attachments/assets/c609666e-582e-4521-be08-20b3ccd2bd70" />
<img width="1920" height="880" alt="Screenshot (797)" src="https://github.com/user-attachments/assets/03c14ad1-034a-4171-95ea-10d11092b07d" />
<img width="1920" height="869" alt="Screenshot (799)" src="https://github.com/user-attachments/assets/8c076eb9-1f15-48e2-b611-d59ce2366d76" />
<img width="1920" height="874" alt="Screenshot (800)" src="https://github.com/user-attachments/assets/03c23c02-543d-4d97-9cd5-e7740d62ba20" />
<img width="1920" height="880" alt="Screenshot (802)" src="https://github.com/user-attachments/assets/bf63a930-9bab-4c59-87a0-8eb83d165690" />
<img width="1920" height="956" alt="Screenshot (803)" src="https://github.com/user-attachments/assets/8fb5ab46-973b-4a89-bcec-edfcee9bba0c" />
<img width="1920" height="884" alt="Screenshot (804)" src="https://github.com/user-attachments/assets/3324d8e6-9cdd-4fd1-9577-341285ff6e52" />
<img width="1920" height="876" alt="Screenshot (805)" src="https://github.com/user-attachments/assets/82b0584a-803f-4efd-995a-a3e3c8f1b386" />
<img width="1920" height="882" alt="Screenshot (806)" src="https://github.com/user-attachments/assets/c1cfce0d-f59c-4855-a591-deb17e7079c6" />
<img width="1920" height="1080" alt="Screenshot (810)" src="https://github.com/user-attachments/assets/f099ad76-4417-4fcb-9607-5af0871cd322" />


---

### **Takeaways**

* **Security groups** act as firewalls controlling inbound/outbound traffic.
* **User Data scripts** automate instance setup during launch.
* **Termination protection** prevents accidental deletion of important resources.
* **Instance resizing** (CPU/RAM) and **EBS volume resizing** are straightforward in AWS.
* Always validate **status checks** and **security rules** after launch.
