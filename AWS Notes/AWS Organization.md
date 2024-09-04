<!-- Jatin Bunkar Notes For AWS Organization --> 
## AWS Organizations

### AWS Organizations Simplified:
AWS Organizations is an account management service that enables you to consolidate multiple AWS accounts into an organization that you create and centrally manage.

### AWS Organizations Key Details:
- Best practices is to use the root account to manage billing only with separate accounts used to deploy resources.
- The point of AWS Organizations is to deploy permissions to the separate accounts underneath the root account and have those policies trickle down. AWS Organizations helps you centrally govern your environment as you grow and scale your workloads on AWS. 
- You can use organizational units (OUs) to group similar accounts together to administer as a single unit. This greatly simplifies the management of your accounts. 
- You can attach a policy-based control to an OU, and all accounts within the OU automatically inherit the policy. So if your company's developers all have their own sandbox AWS account, they can be treated as a single unit and be restricted by the same policies.
- With AWS Organizations, we can enable or disable services using Service Control Policies (SCPs) broadly on organizational units or more specifically on individual accounts
- Use SCPs with AWS Organizations to establish access controls so that all IAM principals (users and roles) adhere to them. With SCPs, you can specify *Conditions*, *Resources*, and *NotAction* to deny access across accounts in your organization or organizational unit. For example, you can use SCPs to restrict access to specific AWS Regions, or prevent deleting common resources, such as an IAM role used for your central administrators.
