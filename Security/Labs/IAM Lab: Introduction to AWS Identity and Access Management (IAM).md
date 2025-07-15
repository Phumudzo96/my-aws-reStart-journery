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

<img width="1920" height="873" alt="Screenshot (675)" src="https://github.com/user-attachments/assets/febc9f19-f77d-4826-a438-57328c80661f" />
<img width="1920" height="878" alt="Screenshot (676)" src="https://github.com/user-attachments/assets/20cd72f0-b7b2-4f8f-a2ce-5ac4067a4e0b" />
<img width="1920" height="876" alt="Screenshot (677)" src="https://github.com/user-attachments/assets/21960624-e594-42d7-9d44-30c47ae894c7" />
<img width="1920" height="871" alt="Screenshot (678)" src="https://github.com/user-attachments/assets/ed0f9d2e-eca8-4b5e-8e70-9552f913f01d" />
<img width="1920" height="873" alt="Screenshot (679)" src="https://github.com/user-attachments/assets/538dc8cb-908f-4dac-aac6-b3c3addd0b9b" />
<img width="1920" height="892" alt="Screenshot (680)" src="https://github.com/user-attachments/assets/ad4da96c-4aef-4180-b3cb-d97738e4421b" />
<img width="1920" height="877" alt="Screenshot (681)" src="https://github.com/user-attachments/assets/41e55494-6461-44c7-a565-fde24089b965" />
<img width="1920" height="881" alt="Screenshot (682)" src="https://github.com/user-attachments/assets/3aad60d8-e8f1-4560-b02d-76c6fe4c36f6" />
<img width="1920" height="881" alt="Screenshot (683)" src="https://github.com/user-attachments/assets/bdd88bba-f5cc-4952-b53a-3d439f7c3676" />
<img width="1920" height="874" alt="Screenshot (684)" src="https://github.com/user-attachments/assets/3ec7eeb7-ff4e-4ce0-bec5-2677a5f4f2bb" />
<img width="1920" height="883" alt="Screenshot (685)" src="https://github.com/user-attachments/assets/51bc03f0-83ce-4b2d-b687-1f8bb6b9c646" />



## Takeaways
IAM allows granular control over user permissions across AWS services.

Managed policies are reusable and automatically update across users/groups.

Inline policies are custom policies tied to a single user/group.

Always verify Region when resources are not visible during IAM user tests.

Testing IAM permissions by signing in as different users is crucial for validation before handing off credentials in production.


## Architectural diagram

<img width="1920" height="888" alt="Screenshot (686)" src="https://github.com/user-attachments/assets/974350cc-d44e-424f-baa9-e83b83c35b6b" />
