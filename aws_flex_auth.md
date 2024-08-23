# IAM Users, Groups, Roles, and Policies
## IAM Users and Groups:
**IAM Users:** Individual users with their own set of credentials for accessing AWS services. Focus on creating least-privilege users.
IAM Groups: Collections of users that share the same permissions. Use groups to simplify management and apply policies at a group level rather than individually.
## IAM Roles:
**IAM Roles:** Assumeable entities that can be used by AWS services, users, or applications. Roles do not have credentials like users but are assumed temporarily.
**Cross-Account Access:** Allow users from one AWS account to access resources in another account.
**Service Roles:** Grant AWS services permissions to act on your behalf (e.g., EC2 instances accessing S3 buckets).
## IAM Policies:
**Managed Policies:** Reusable policies that can be attached to multiple users, groups, or roles. AWS provides AWS Managed Policies, but you can create your own.
**Inline Policies:** Policies embedded directly into a single user, group, or role. They provide a one-to-one relationship.
Policy Elements: Understand policy syntax, including actions, resources, and conditions to specify precise permissions.
# Principle of Least Privilege
- Ensure that users, groups, and roles have only the permissions they need to perform their tasks. Regularly review and refine policies to remove unnecessary permissions.

## Access Control Mechanisms
** MFA (Multi-Factor Authentication):** Enforce MFA for sensitive operations and privileged accounts to add an extra layer of security.
## Role-Based Access Control (RBAC):
- Define roles based on job functions and assign permissions accordingly.
Attribute-Based Access Control (ABAC):
Use attributes (e.g., tags) to create dynamic, context-aware permission models.
#  Policy Management and Evaluation
## Policy Simulation:
Use IAM Policy Simulator to test and validate the effect of policies before deploying them.
Policy Versioning:
Maintain different versions of policies and revert to previous versions if necessary.
# Auditing and Monitoring
## CloudTrail:
- Enable AWS CloudTrail to log API calls and monitor IAM activities for auditing and compliance purposes.
## Cloudwatch
- **GetMetricData** action can show the IOPS and throughput of an io2 volume to help you determine if the io2 volume is a good candidate for modification to a lower-cost volume type 
## AWS Config:
- Use AWS Config to track configuration changes to IAM resources and ensure compliance with security policies.
Access Analyzer:
AWS IAM Access Analyzer helps identify resources that are shared with external entities and analyze policies for potential over-permissiveness.
# Best Practices and Recommendations
**Separation of Duties:** Ensure different roles and permissions for development, testing, and production environments.
**Use of Temporary Credentials:** Leverage temporary security credentials via IAM roles and AWS STS to reduce the risk associated with long-term credentials.
Regular Audits: Periodically audit IAM policies and access controls to ensure they meet the security requirements and compliance standards.
# Advanced Security Features
Resource-Based Policies: Apply policies directly to AWS resources, like S3 buckets or SQS queues, for additional control.
Service Control Policies (SCPs): Use SCPs in AWS Organizations to enforce permission boundaries across accounts.
Identity Federation: Implement SSO and federated access using SAML, OpenID Connect, or custom identity brokers.

## EMR
Elastic map reduce is a serverless way to process data 

## Amazon FSx
Amazon fsx for netapp is a NAS architecture file system for storage data 
This is a NAS or NFS and uses smb protocol

## S3 
- Security- Use Origin access control with cloudfront distriburtion to update the bucket policy to grant permissions to prevent users from accessing the assessets in the S
bucket

## CloudFront
 - a web service that speeds up distribution of your static and dynamic web content, such as .html, .css, .js, and image files, to your users. CloudFront delivers your content through a worldwide network of data centers called edge locations
 - CloudFront provides two ways to send authenticated requests to an Amazon S3 origin: origin access control (OAC) and origin access identity (OAI). OAC helps you secure your origins, such as for Amazon S3. We recommend using OAC because it supports:
	- All Amazon S3 buckets in all AWS Regions, including opt-in Regions launched after December 2022
   - Amazon S3 server-side encryption with AWS KMS (SSE-KMS)
   - Dynamic requests (PUT and DELETE) to Amazon S3