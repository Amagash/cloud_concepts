# Identity and Access Management (IAM)
## Securing the root Account
The root account is the email address you used to sign up for AWS. The root account has full administrative access to AWS so it is important to secure this account. 

Best Practices:
- Turn on MFA on your root account: in IAM dashboard go to "rotate credentials" and "Activate MFA".
- Create an admin group for your admins and assign appropriate permissions
- Search if the policy you need doesn't already exist in AWS managed policies before of creating yours
  

## Controlling User's Actions with IAM Policy Documents
We can assign Policy documents to groups, users and roles. The best practice is to create a group and put users in the groups who are going to inherits the permissions from the group.

Policy documents are JSON like so :
```json
{
  "Version": "2012-10-17",
  "Statement": [
        {
        "Sid": "FirstStatement",
        "Effect": "Allow",
        "Action": ["iam:ChangePassword"],
        "Resource": "*"
        }
    ]
}
```

The information in a statement is contained within a series of elements.

- **Version** – Specify the version of the policy language that you want to use. As a best practice, use the latest 2012-10-17 version.

- **Statement** – Use this main policy element as a container for the following elements. You can include more than one statement in a policy.

- **Sid** (Optional) – Include an optional statement ID to differentiate between your statements.

- **Effect** – Use Allow or Deny to indicate whether the policy allows or denies access.

- **Principal** (Required in only some circumstances) – If you create a resource-based policy, you must indicate the account, user, role, or federated user to which you would like to allow or deny access. If you are creating an IAM permissions policy to attach to a user or role, you cannot include this element. The principal is implied as that user or role.

- **Action** – Include a list of actions that the policy allows or denies.

- **Resource** (Required in only some circumstances) – If you create an IAM permissions policy, you must specify a list of resources to which the actions apply. If you create a resource-based policy, this element is optional. If you do not include this element, then the resource to which the action applies is the resource to which the policy is attached.

- **Condition** (Optional) – Specify the circumstances under which the policy grants permission.

## Permanent IAM Credentials
- User = one Physical person, no more
- Groups = Functions, such as admins, developers, etc.
- Roles = Internal usage within AWS

The principle of least privilege: Only assign a user the minimum amount of privileges they need to do their job.

You can search for policies by job function. You can modify password policy.

## IAM Exam Tips
### Secure your AWS root account:
- Enable MFA
- Create an admin group for admins and assign appropriate permissions to the group
- Create user accounts for administrators
- Add your users to the group
- DO NOT login with the root account on a daily basis


### Assign permission using IAM Policy documents (JSON)
- Be able to read a IAM Policy document

### IAM credentials
- IAM is Universal: it does not apply to regions at this time.
- New users: No permissions when first created
- Access key ID and secret access keys are not the same as usernames and passwords
- You only get to view these once so keep them in a secure place. If lost, regenerate them.
- Always password rotation: customize you password policies.
- IAM federation: You can combine your existing user account with AWS.
- Identity Federation: Uses SAML standard which is Active Directory.