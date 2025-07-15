# Monitoring Infrastructure Lab
## Objective
Learn how to monitor applications and infrastructure using CloudWatch and AWS Config.

## Steps Taken
Logged into AWS Console

Launched EC2 instance (Ubuntu)

Installed CloudWatch agent using Systems Manager Run Command

Configured CloudWatch agent with Parameter Store

Shipped application logs (access & error logs) to CloudWatch Logs

Created metric filter to detect 404 errors in web server logs

Created a CloudWatch Alarm to notify on too many 404s

Subscribed email to SNS topic to receive alerts

Explored instance-level metrics via CloudWatch and CloudWatch agent

Created CloudWatch Events rule to notify when instance is stopped or terminated

## Challenges
Required IAM permissions to use Systems Manager and CloudWatch agent
✅ Solved by attaching the proper IAM role to the instance

Initial logs didn’t appear instantly
✅ Solved by generating web traffic and waiting for logs to sync

## Screenshot
<img width="1920" height="876" alt="Screenshot (687)" src="https://github.com/user-attachments/assets/a322d6bd-7d78-4f18-9c10-2df73fc393d7" />
<img width="1920" height="876" alt="Screenshot (688)" src="https://github.com/user-attachments/assets/3d97469c-3f45-4147-b7f8-0010bb3d929f" />
<img width="1920" height="869" alt="Screenshot (689)" src="https://github.com/user-attachments/assets/71def70a-af21-4922-b39d-011724343f99" />
<img width="1920" height="862" alt="Screenshot (690)" src="https://github.com/user-attachments/assets/6199dd19-df72-4183-b69f-7380ed18baaf" />
<img width="1920" height="886" alt="Screenshot (691)" src="https://github.com/user-attachments/assets/0d1d8453-8812-41af-be19-28f0b9f74bea" />
<img width="1920" height="876" alt="Screenshot (692)" src="https://github.com/user-attachments/assets/4141c966-ff97-4a13-a8f4-7face4b1d5f4" />
<img width="1920" height="853" alt="Screenshot (693)" src="https://github.com/user-attachments/assets/2605151e-171a-4184-b0d6-fbcc36cfc482" />
<img width="1920" height="880" alt="Screenshot (694)" src="https://github.com/user-attachments/assets/3c8f9622-906d-4f1b-9750-72f37a9871ca" />
<img width="1920" height="869" alt="Screenshot (695)" src="https://github.com/user-attachments/assets/dec414f2-e0c3-434d-bd6b-c60b866f8160" />
<img width="1913" height="869" alt="Screenshot (696)" src="https://github.com/user-attachments/assets/a0d526ca-b34e-458e-92d5-528b6f079acd" />
<img width="1920" height="862" alt="Screenshot (697)" src="https://github.com/user-attachments/assets/9192796e-ad4c-496e-94c0-9cb23bf73d08" />
<img width="1920" height="865" alt="Screenshot (698)" src="https://github.com/user-attachments/assets/a0d1236e-029c-4ba4-9f7e-0bb5144cc682" />



## Takeaways
CloudWatch provides powerful log, metric, and event monitoring for infrastructure.

CloudWatch agent gives deeper visibility into inside-the-instance metrics.

Parameter Store can securely store agent configs.

Metric Filters & Alarms enable proactive monitoring and alerting.

CloudWatch Events automate notifications for infrastructure changes.

Monitoring is essential for operational excellence and quick incident response.
