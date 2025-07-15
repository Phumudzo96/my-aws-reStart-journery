# Monitoring Lab: Working with AWS CloudTrail
## Objective
Learn how to create a CloudTrail trail, analyze logs using Athena and CLI, and investigate unauthorized changes in an AWS environment.

## Steps Taken
Logged into AWS Console

Launched the activity environment with a pre-configured Café Web Server (EC2)

Modified the security group to allow SSH from my IP

Created a CloudTrail trail with a new S3 bucket for logs

Observed the website being hacked (unauthorized image injected)

SSH’d into the EC2 instance

Downloaded and extracted CloudTrail logs using AWS CLI

Analyzed logs using:

grep for specific IPs and event names

AWS CLI cloudtrail lookup-events with filters

Amazon Athena for SQL-based log analysis

Identified:

Who modified the security group

Time and method of the hack

Hacker’s IP and user identity

Removed unauthorized OS users on the EC2 instance

Updated SSH configuration to disable password authentication

Removed insecure security group rule (port 22 open to 0.0.0.0/0)

Restored the original website image

## Challenges
Log delay: CloudTrail logs took ~5 minutes to appear in S3; required waiting before download.

SSH Configuration: Detected password-based SSH was enabled, which is insecure.

Active unauthorized user: Had to identify and forcibly remove the chaos-user while managing active sessions.

## Screenshot
<img width="1920" height="1080" alt="Screenshot (699)" src="https://github.com/user-attachments/assets/643e93d5-5b82-4805-a104-337f3bf73885" />
<img width="1920" height="1080" alt="Screenshot (700)" src="https://github.com/user-attachments/assets/47dfca56-251b-41dc-ba3f-2d8eb9700250" />
<img width="1920" height="1080" alt="Screenshot (702)" src="https://github.com/user-attachments/assets/e5a4fab8-347d-4dea-91e7-b5aafba34b86" />
<img width="1920" height="1080" alt="Screenshot (703)" src="https://github.com/user-attachments/assets/5f6601d0-2858-4961-a329-7f715065c7f5" />
<img width="1920" height="1080" alt="Screenshot (704)" src="https://github.com/user-attachments/assets/1ba40237-ddbd-41b5-b782-4f2487b6e507" />
<img width="1920" height="1080" alt="Screenshot (705)" src="https://github.com/user-attachments/assets/6fcfaff9-8fb1-42fb-b782-3b4e4d5541ae" />
<img width="1920" height="1080" alt="Screenshot (706)" src="https://github.com/user-attachments/assets/1fa4c49f-04e4-4280-bfe6-5bf666af394a" />
<img width="1920" height="1080" alt="Screenshot (707)" src="https://github.com/user-attachments/assets/e03b452e-7254-431d-a814-e7b77a4b780b" />
<img width="1920" height="1080" alt="Screenshot (708)" src="https://github.com/user-attachments/assets/1d521020-73d2-4e18-bdfe-aeeabcf2fc9e" />
<img width="1920" height="1080" alt="Screenshot (709)" src="https://github.com/user-attachments/assets/cac8e5d7-98be-473a-a6ad-a23e3ba084c1" />
<img width="1920" height="1080" alt="Screenshot (710)" src="https://github.com/user-attachments/assets/8417570f-2f07-4215-a34e-3fcf7319b6ee" />
<img width="1920" height="1080" alt="Screenshot (711)" src="https://github.com/user-attachments/assets/1b7bcf7b-3720-467a-a5f8-690d4ddaf138" />


## Takeaways
✅ CloudTrail is critical for tracking AWS API activities for security investigations.

✅ Athena provides a scalable, SQL-based approach for filtering and analyzing JSON-based CloudTrail logs quickly.

✅ Always secure SSH by disabling password authentication and using key pairs.

✅ Security groups act as firewalls; review and restrict inbound rules regularly to prevent unauthorized access.

✅ CloudTrail, CLI, and Athena together provide a powerful toolset for incident detection and response in AWS.
