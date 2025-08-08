# **Monitoring Infrastructure**

### Objective

Learn how to monitor applications and infrastructure using AWS CloudWatch and AWS Config.

---

### Steps Taken

* Launched lab and logged into AWS Console.

* Used AWS Systems Manager Run Command to install and configure the CloudWatch agent on an EC2 instance (Web Server).

* Configured CloudWatch agent to collect system metrics (CPU, disk, memory) and web server logs.

* Created CloudWatch Logs metric filters to detect 404 errors in access logs.

* Set up CloudWatch alarm to notify via email when 404 error rate exceeds threshold.

* Viewed EC2 instance metrics via CloudWatch Console.

* Created CloudWatch Events rule to send notifications when EC2 instance state changes (stopped or terminated).

* Verified real-time notifications via email.

* Activated AWS Config rules to monitor infrastructure compliance for resource tagging and unattached EBS volumes.

---

### Challenges

* Ensuring correct parameter store configuration for CloudWatch agent.
  
* Waiting for metrics and logs to propagate before alarms trigger.

* Managing AWS Config rules initial resource evaluation delay.

---

### Screenshot

<img width="1920" height="882" alt="Screenshot (699)" src="https://github.com/user-attachments/assets/5ab2df71-213f-4ff6-920d-6977295082e4" />
<img width="1920" height="865" alt="Screenshot (700)" src="https://github.com/user-attachments/assets/da471c0b-d2a2-4e00-b89c-be5266c06961" />
<img width="1920" height="935" alt="Screenshot (701)" src="https://github.com/user-attachments/assets/ace7c9b2-0a4f-44c0-a5b8-6f2a850a2ce6" />
<img width="1920" height="862" alt="Screenshot (702)" src="https://github.com/user-attachments/assets/49248585-2aa0-44eb-8e1a-f9c38e0e844a" />
<img width="1920" height="1009" alt="Screenshot (703)" src="https://github.com/user-attachments/assets/9a8cb890-22f3-4d3f-a7f0-be8ef583bb4a" />
<img width="1920" height="1021" alt="Screenshot (704)" src="https://github.com/user-attachments/assets/229532fa-fa17-492d-84d1-3a73769f3768" />
<img width="1920" height="1013" alt="Screenshot (705)" src="https://github.com/user-attachments/assets/768d29f4-d2c4-48be-84bf-8fdd18945808" />
<img width="1920" height="1000" alt="Screenshot (706)" src="https://github.com/user-attachments/assets/0f1bfbf9-4584-492f-af98-e9d30281e676" />
<img width="1920" height="1005" alt="Screenshot (707)" src="https://github.com/user-attachments/assets/298724be-6eba-45eb-92c9-fdf99b7be2fa" />
<img width="1920" height="873" alt="Screenshot (708)" src="https://github.com/user-attachments/assets/5f83d855-dd46-4a90-acec-fe40bcb2ddfc" />
<img width="1920" height="875" alt="Screenshot (709)" src="https://github.com/user-attachments/assets/3de36816-432a-4f12-bb00-fc7ed1ff1bb1" />
<img width="1920" height="891" alt="Screenshot (710)" src="https://github.com/user-attachments/assets/f1f8d272-ee81-4d68-80ed-5339c7e17fff" />
<img width="1920" height="1009" alt="Screenshot (711)" src="https://github.com/user-attachments/assets/714127a6-e005-4b9a-bd16-b5596754399a" />


---

### Takeaways

* CloudWatch agent enhances monitoring inside EC2 instances beyond standard metrics.

* Metric filters and alarms enable proactive alerting based on log data.

* CloudWatch Events provide real-time operational notifications.

* AWS Config helps maintain compliance and governance by continuously auditing resources.

* Effective monitoring requires proper setup and patience for data collection and alerts to activate.

---
