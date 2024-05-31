# Identity and Access Management (IAM)

- Identities used to authenticate in an AWS account
- Each IAM user is unique to an AWS account
- Access mangement decides what resources a user can use once the ID has been authenticated
- IAM is only as strong as how you implement it as the owner of the AWS account

## Access Management

- Users:
  - Object created to represent an ID (either human or an application) to interact with resources in the account
  - Each has a unique Amazon Resource Name (ARN)
- Groups:
  - Used to authorise groups of users using IAM policies assigned to that group
- Roles:
  - Allow users to an AWS service to temporarily adopt a set of permissions
  - They don't define a single user, they are designed to be used by multiple users who need to adopt the set of permissions
  - They can be adopted so long as the user has permission to adopt them
- Policies:
  - These are JSON documents which can be attached to Users, Groups or Roles
  - These can be managed policies which are predefined by AWS or customer managed policies
  - Or inline policy whcih are done inline of the JSON document
- Identity Provider:
  - Allows federated access (external credentials to AWS are granted access to AWS resources)
- Security Token Service Endpoint:
  - Allows you to request temporary, limited-privaledge credentials for both IAM and federated users

## Access Report

- Access Analyzer:
  - Reports on any resource which allows access to an external resource outside of the AWS account
- Credential Report:
  - Produces a file of all an account's users and their credential details
- Organisational Activity:
  - Monitor service activity for users
- Service Control Policies:
  - Lists any service control policies and affected users
  - SCP can deny access to AWS services and override any existing permissions for a user

## Managing IAM - User Identities

### Managing Users

- Path:
  - Can be used to determine where users sit in the organisation structure (e.g. /Content/UK/Web)
  - This can be referenced in policies
- Access Key:
  - Allows programatic access to AWS resources
  - Made up of an Access Key ID and Secret Key Access

### Managing Groups

- User Groups are associated with IAM policies
- Users can be attached to a group
- These policies can be AWS or customer defined or inline
- A group can contain up to 10 policies and a user can be associated with up to 10 different groups

### Managing Roles

- Allows users to adopt an ID whith a set of associated policies temporarily
- They can be used by multiple users
- A new set of credentials are created each time a user assumes the wall
- There are Trusts which define who or what can assume the role
- Service roles:
  - Allow AWS services to assume a role to get access to other AWS resources
  - e.g. EC2 instance gets a role to access AWS S3
- Service-linked restrict which service can assume a role to access other resources

### Managing Federated Access

- Identity Federation: Two different providers establish a level of trust between them
- Identity Provider: Authenticates the user
- Service Provider: Controls access to the resources

## IAM Policies

### Policy Types

- Identity-based policies:
  - Assigned to an identity (user, role, group)
  - Controls what permissions each entity has
  - Can be managed (saved within the IAM Policy library and be attached to the entity)
  - Or inline (attributed to a specific entity)
- Resource-based policies:
  - Inline policy defined on the resource
  - Has a Trust Relationship Policy
  - Resource is the role
  - RBP is the trust relationship
  - Uses a Principle in the policy definition (to determine which ID it relates to)
- Permission Boundaries:
  - Only can be applied to a user or role (not a group)
  - Doesn't grant permissions but prevents a user or a role from accessing certain permissions
- Organisation Service Control Policies (SCPs)
  - Attached so AWS Accounts or Organisational Units (OUs)
  - Act like a Permission Boundary but for the wider organisation/account
  - Has to be modified from the AWS Organisation service rather than IAM

### Policy JSON Structure

- SID: Optional parameter, allows you to assign a Statement ID (e.g."AllowReadss3")
- Effect: Allow or Deny access
- Principle: Which policy it relates to (only for resource-based policies)
- Action: For example, S3:DeleteBucket
- Resource: Resource which the policy is to be applied to (by ARN)
- Condition: Condition for when to apply the policy (e.g. user must authenticate using MFA)
