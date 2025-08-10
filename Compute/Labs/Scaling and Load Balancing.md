# **Scaling and Load Balancing** 

---

## **Objective**
Learn how to create a scalable, load-balanced architecture on AWS using an Application Load Balancer and Auto Scaling Group.

---

## **Steps Taken**

1. Logged into AWS Console.
2. Created an AMI from the existing **Web Server 1** instance.
3. Created an **Application Load Balancer** (LabELB) across two public subnets.
4. Created a **Target Group** (`lab-target-group`) and linked it to the ALB.
5. Created a **Launch Template** (`lab-app-launch-template`) using the Web Server AMI.
6. Created an **Auto Scaling Group** in two private subnets (min 2, max 4 instances) with CPU target tracking at 50%.
7. Verified that ALB was routing traffic to healthy instances.
8. Simulated high CPU load using the Load Test app to trigger Auto Scaling.
9. Observed new instances launching in response to the CloudWatch alarm.
10. Terminated the original Web Server 1 instance.

---

## **Challenges**

* **Instance type unavailable**: t3.micro was unavailable in the region.

  * **Solution**: Switched to t2.micro in the launch template.
* **Target group health checks delayed**: Instances took time to show as “healthy.”

  * **Solution**: Waited for health check intervals to pass before testing.

---

## **Screenshot**
<img width="1920" height="865" alt="Screenshot (811)" src="https://github.com/user-attachments/assets/26f98103-c59c-4511-a666-5d55b0ff435b" />
<img width="1920" height="865" alt="Screenshot (812)" src="https://github.com/user-attachments/assets/f9cb4cff-88b1-4bb6-8a69-533f2be51024" />
<img width="1920" height="873" alt="Screenshot (813)" src="https://github.com/user-attachments/assets/81a9a8c1-ad87-4de4-bdf5-1f0262ec505f" />
<img width="1920" height="880" alt="Screenshot (814)" src="https://github.com/user-attachments/assets/ee71e4ab-9d96-41b5-8f5c-3c5f10206cb0" />
<img width="1920" height="873" alt="Screenshot (815)" src="https://github.com/user-attachments/assets/42fb6868-0510-4553-b046-f4985617fd7b" />
<img width="1920" height="876" alt="Screenshot (816)" src="https://github.com/user-attachments/assets/ab25a624-b0a4-449d-849c-0109556003b3" />
<img width="1920" height="876" alt="Screenshot (817)" src="https://github.com/user-attachments/assets/ba601466-5d88-4a08-af4b-4c0cb270afd7" />
<img width="1920" height="876" alt="Screenshot (817)" src="https://github.com/user-attachments/assets/a2eeeafe-828e-481b-b11b-ae330acae1ab" />
<img width="1903" height="862" alt="Screenshot (818)" src="https://github.com/user-attachments/assets/98f59fd2-a320-4c2f-982c-5ab6c6b9ef28" />
<img width="1903" height="862" alt="Screenshot (818)" src="https://github.com/user-attachments/assets/48e91dcd-62b3-4bdd-bda1-9f3e0bc3a2eb" />
<img width="1916" height="891" alt="Screenshot (819)" src="https://github.com/user-attachments/assets/48532c3d-8521-48ee-9c2f-cd300c8a04aa" />
<img width="1916" height="891" alt="Screenshot (819)" src="https://github.com/user-attachments/assets/672cb8f7-b424-4201-a6fb-30ed579e68a4" />
<img width="1920" height="876" alt="Screenshot (820)" src="https://github.com/user-attachments/assets/6b2deb5b-6114-45a4-9ea8-ce519751dccc" />
<img width="1920" height="876" alt="Screenshot (820)" src="https://github.com/user-attachments/assets/57d44734-03a7-45cd-8372-9535e43ef978" />
<img width="1920" height="889" alt="Screenshot (821)" src="https://github.com/user-attachments/assets/674343fc-2f7a-48e5-82ce-d6d3f015a9f9" />
<img width="1920" height="884" alt="Screenshot (822)" src="https://github.com/user-attachments/assets/9051512f-8e79-4ba1-a23a-7814d30e8e1b" />
<img width="1917" height="870" alt="Screenshot (825)" src="https://github.com/user-attachments/assets/baeef59c-afd4-4b24-82f5-bbcb083a8953" />
<img width="1920" height="876" alt="Screenshot (826)" src="https://github.com/user-attachments/assets/5be1dcd7-5298-4d92-b4d5-5aa2c0e7a0ed" />
<img width="1920" height="1080" alt="Screenshot (827)" src="https://github.com/user-attachments/assets/52c05770-ca73-410c-8f6f-03fe97f5e3e4" />

---

## **Takeaways**

* Application Load Balancers improve fault tolerance by distributing traffic across multiple AZs.
* Auto Scaling Groups maintain desired capacity and scale based on defined metrics.
* Health checks ensure traffic is only sent to healthy instances.
* Always verify subnet placement (public for ALB, private for instances) for security and proper routing.
