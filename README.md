Q.
create a terraform script to do below

iam user creation with tags (based on servicenow request) no groups

add one policy (s3 read) to user

- generate a new access and secret keys and download it

- send mail with iam user arn and keys over mail
=========================================================================================================

Steps to Implement:
Set up Terraform Configuration
1. Create a Terraform configuration file (main.tf) to define the IAM user, policy, and keys.
2. Define IAM User
Create an IAM user and add tags from a ServiceNow request.
3. Attach an S3 Read-Only Policy
Attach the AWS-managed S3 Read-Only policy to the user.
4. Generate Access & Secret Keys
Create and store IAM user credentials.
5. Store Credentials Securely
Save the keys in a file (e.g., creds.json).
6. Send Email with Credentials
Use AWS SES or a local SMTP server to send credentials via email.

-------------------------------------------------------------------------------------------
How It Works:
Creates an IAM User (servicenow-user)
Assigns an S3 Read-Only Policy
Generates IAM Access & Secret Key
Stores the credentials securely in AWS Secrets Manager
Sends an email notification via AWS SES
The email contains retrieval instructions (NOT credentials)
The requester can securely fetch credentials using AWS CLI
----------------------------------------------------------------------------------------------------------------
Benefits:
✅ No plaintext credentials sent via email
✅ Secrets are stored securely in AWS Secrets Manager
✅ Requester retrieves credentials securely via AWS CLI
✅ Automatic email notification to requester

Would you like me to add a IAM policy to restrict secret access to specific users