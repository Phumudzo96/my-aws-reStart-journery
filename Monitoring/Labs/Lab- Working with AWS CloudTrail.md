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
<img width="1920" height="882" alt="Screenshot (699)" src="https://github.com/user-attachments/assets/6124add1-a101-4e47-a4ec-f091b50bd20e" />
<img width="1920" height="865" alt="Screenshot (700)" src="https://github.com/user-attachments/assets/ebf75a55-2023-4459-82b7-17cf4bca1ec0" />
<img width="1920" height="862" alt="Screenshot (702)" src="https://github.com/user-attachments/assets/51c8eb5e-0a97-4e5b-ba68-7268f1bc5c47" />
<img width="1920" height="1009" alt="Screenshot (703)" src="https://github.com/user-attachments/assets/9aeb8547-86e4-4585-ac3c-b53a872621e0" />
<img width="1920" height="1021" alt="Screenshot (704)" src="https://github.com/user-attachments/assets/1a94ba4e-3e73-475f-9c83-5e42835a131f" />
<img width="1920" height="1013" alt="Screenshot (705)" src="https://github.com/user-attachments/assets/73034387-9bc3-437d-a8c2-f1213db9db9b" />
<img width="1920" height="1000" alt="Screenshot (706)" src="https://github.com/user-attachments/assets/8ac25db0-88a5-4d33-ae55-e8f0ba3f9574" />
<img width="1920" height="1005" alt="Screenshot (707)" src="https://github.com/user-attachments/assets/8466eb5b-2b61-411d-aecc-372b0aa43c74" />
<img width="1920" height="873" alt="Screenshot (708)" src="https://github.com/user-attachments/assets/8318f20d-8a5f-4744-b938-606d10453269" />
<img width="1920" height="875" alt="Screenshot (709)" src="https://github.com/user-attachments/assets/2221baa4-c5e4-484e-bd8e-261ef183dbac" />
<img width="1920" height="891" alt="Screenshot (710)" src="https://github.com/user-attachments/assets/d0c7ea7f-428e-4ce8-9edf-a15f3bd1c9b2" />
<img width="1920" height="1009" alt="Screenshot (711)" src="https://github.com/user-attachments/assets/a961038f-5d82-469d-b816-79b3a2cff71e" />



## Takeaways
✅ CloudTrail is critical for tracking AWS API activities for security investigations.

✅ Athena provides a scalable, SQL-based approach for filtering and analyzing JSON-based CloudTrail logs quickly.

✅ Always secure SSH by disabling password authentication and using key pairs.

✅ Security groups act as firewalls; review and restrict inbound rules regularly to prevent unauthorized access.

✅ CloudTrail, CLI, and Athena together provide a powerful toolset for incident detection and response in AWS.

## Architectural diagram

<img width="829" height="503" alt="Working with AWS CloudTrail drawio" src="https://github.com/user-attachments/assets/6bfc506c-4a06-4c09-b5fe-de5895b9f475" />

