# IAM Lab: Introduction to AWS Identity and Access Management (IAM)
Objective
Learn how to create and apply IAM password policies, explore IAM users and groups, attach policies, add users to groups, and test permissions by signing in as each user.

## Steps Taken
Logged into AWS Console

Created a custom IAM password policy (10 characters minimum, complexity requirements, 90-day expiration)

Explored pre-created IAM users (user-1, user-2, user-3) and groups (EC2-Admin, EC2-Support, S3-Support)

Inspected attached managed and inline IAM policies

Added:

user-1 to S3-Support (read-only S3 access)

user-2 to EC2-Support (read-only EC2 access)

user-3 to EC2-Admin (view/start/stop EC2 instances)

Located IAM user sign-in URL

Signed in as each user to test permissions:

user-1 could view S3 buckets, could not view EC2 instances

user-2 could view EC2 instances, could not stop instances, could not view S3 buckets

user-3 could view and stop EC2 instances

## Challenges
Initially forgot to note the AWS Region, leading to empty EC2/S3 views

Solved by switching to the correct Region noted at the start of the lab

## Screenshot
<img width="1920" height="1080" alt="Screenshot (675)" src="https://github.com/user-attachments/assets/bee5e22e-da12-4d8a-94c4-0b271456dadb" />
<img width="1920" height="1080" alt="Screenshot (676)" src="https://github.com/user-attachments/assets/1696e5b2-8200-4e4b-ba75-39dc2cff6cdd" />
<img width="1920" height="1080" alt="Screenshot (677)" src="https://github.com/user-attachments/assets/8760ea84-8cbc-44bb-84c9-89da61a5103f" />
<img width="1920" height="1080" alt="Screenshot (678)" src="https://github.com/user-attachments/assets/70686a52-1c29-4a5a-831e-11ab5c9e9bb6" />
<img width="1920" height="1080" alt="Screenshot (679)" src="https://github.com/user-attachments/assets/cca2d278-faf4-4d9c-ac58-27751015c372" />
<img width="1920" height="1080" alt="Screenshot (680)" src="https://github.com/user-attachments/assets/f5932af2-e7b3-44ad-ab95-aae1c3aa556b" />
<img width="1920" height="1080" alt="Screenshot (681)" src="https://github.com/user-attachments/assets/2923dee0-056c-40bc-b0a9-1bef0e8568db" />
<img width="1920" height="1080" alt="Screenshot (682)" src="https://github.com/user-attachments/assets/7d05b95f-fd91-42d4-bf43-c8c331b400cc" />
<img width="1920" height="1080" alt="Screenshot (683)" src="https://github.com/user-attachments/assets/8d0efed8-8513-4266-bf34-789a4387f4c3" />
<img width="1920" height="1080" alt="Screenshot (684)" src="https://github.com/user-attachments/assets/15deeb43-202f-4cb9-acf9-51be75c5cf4c" />
<img width="1920" height="1080" alt="Screenshot (685)" src="https://github.com/user-attachments/assets/b1520edf-4a95-4be2-8e7a-7a927fe69104" />




## Takeaways
IAM allows granular control over user permissions across AWS services.

Managed policies are reusable and automatically update across users/groups.

Inline policies are custom policies tied to a single user/group.

Always verify Region when resources are not visible during IAM user tests.

Testing IAM permissions by signing in as different users is crucial for validation before handing off credentials in production.
