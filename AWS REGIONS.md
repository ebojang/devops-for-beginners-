AWS region is a cluster of data canters.

Things to consider when choosing AWS regions:
* compliance 
* proximity to customers or low latency 
* available services: not all regions have available services or features
* pricing 

Azure region is made up of multiple availability zones (AZ) 
Each region has min3 data centers and max 6 data centers.
Each availability zone has it's own discrete power supply, networking and connectivity.

IDENTITY & ACCESS MANAGEMENT 

Users - people within your organisation
Groups: only contain users not other groups . 

IAM PERMISSIONS IN AWS 
* users or groups can be assigned policies and these policies define the permissions of the users.
* Apply the least privilege principle.*

IAM Policies Inheritance
* permissions are passed down to users based on their groups.

Inline policies - are type of IAM policy attached to a single IAM user, group or role. inline policies are tied specifically to one identity and do not exist independently. Note: if you delete the user/group/role, the inline policy is deleted

IAM POLICY STRUCTURE AND WHAT EACH LINEA MEANS 
{
  "Version": "2012-10-17",
"Id" : "S3-Account-permissions",
  "Statement": [
    {
      "Sid": "S3AccessForApp",
      "Effect": "Allow",
      "Action": [
        "s3:GetObject",
        "s3:PutObject"
      ],
      "Resource": "arn:aws:s3:::my-app-bucket/*"
    }
  ]
}

Version - policy language version 
ID: identifier for the policy (optional)
Statement: main block defining permissions
inside each statement:
- **Sid** _(optional)_ – Label for easier reference.
- **Effect** – `Allow` or `Deny`.
- **Principal** – _Who_ the policy applies to (user, role, account).
- **Action** – _What_ they can do  or cannot do (e.g., `s3:GetObject`, `ec2:StartInstances`).
- **Resource** – _list of resources to which the actions applied to (ARN of bucket, instance, etc.).    
- **Condition** _(optional)_ – _When/if_ the rule applies (e.g., specific IP, time, MFA).

- HOW TO ACCESS AWS?
- * AWS Management console, AWS CLI AND AWS SOFTWARE Developer Kit
 
  * note:
  * Access key ID - acts as your username
  * Secret Access Key - act as your password
  * * Access keys are used to authenticate when using AWS cli or AWS SDK
   
    On CLI, you can run:
    aws iam list-users : this will show list of users you have

     IAM roles let AWS services (like EC2, Lambda, or CloudFormation) securely access other AWS resources without using long-term credentials
 IAM roles = temporary, controlled access for AWS services — secure, flexible, and no exposed credentials.

IAM SECURITY TOOLS
1) IAM Credentials Report (account-level)
* a report that lists all your account's users and the status of their various credentials.
2) IAM Access Advisor (user-level)
  * access advisor shows the service permissions granted to a user and when those services were last accessed.



AMAZON COMPUTE 

EC2- Elastic Compute Service OR Cloud 
* EC2 is an Infrastructure as a Service (IaaS) : renting virtual machine from AWS, data is stored ina virtual drive .
* EC2 can be scaled using an auto-scaling group (ASG) 

EC2 USER DATA SCRIPT
* This is a script that runs when you launch or start an EC2 instance.
  USES OF EC2 DATA SCRIPT:
  * EC2 data scripts can be used to automate boot tasks such as : installing updates, installing software etc



