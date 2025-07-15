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



## Takeaways
IAM allows granular control over user permissions across AWS services.

Managed policies are reusable and automatically update across users/groups.

Inline policies are custom policies tied to a single user/group.

Always verify Region when resources are not visible during IAM user tests.

Testing IAM permissions by signing in as different users is crucial for validation before handing off credentials in production.


## Architectural diagram

<img width="1920" height="888" alt="Screenshot (686)" src="https://github.com/user-attachments/assets/974350cc-d44e-424f-baa9-e83b83c35b6b" />
