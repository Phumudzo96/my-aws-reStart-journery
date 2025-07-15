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


## Takeaways
CloudWatch provides powerful log, metric, and event monitoring for infrastructure.

CloudWatch agent gives deeper visibility into inside-the-instance metrics.

Parameter Store can securely store agent configs.

Metric Filters & Alarms enable proactive monitoring and alerting.

CloudWatch Events automate notifications for infrastructure changes.

Monitoring is essential for operational excellence and quick incident response.
