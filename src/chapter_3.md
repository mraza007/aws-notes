# IAM (Identity Access Management)
- Its a service that provides `users`,`groups`,`IAM policies`.

- **IAM USER**: Its an entity that represents a person or a service and you associate **IAM Policy** directly with the user and it defines its permissions and what the user is allowed to do within `AWS` environment. Furthermore, a user can be assigned the following.
    + An access `key-pair` that allows user programmatic access to the `AWS API`,`CLI`,`SDK` and other development tools.
    + A password for access to the management console.
    + By default users can't do anything within their accounts.
    + the account user crendentials are usually the email address used to create the account and a password.
    + Root account has full admin priviledges and you can think of it as `sudo`.
    + The best practice is to not use the root crendentials instead create an IAM user assign admin priviledges
    + Never share root crendentials.
    + Make sure you enable `MFA`.
    + IAM users can be created to represent applications and these are known as service accounts
    + You can have upto 5000 users per `AWS` account.
    + Each user account has a friendly name and an ARN(Amazon Resource Name) which uniquely identifies the user across AWS.
    + You should always create individual IAM accounts for the users(Not to share them).
    + A password policy can be defined for users enforcing them to have stronger passwords (applies to all users)

- **IAM GROUP**: Its a collection of users that have policies attached to them such as group for  _developers_,_sys-admins_ .
    + Its not an identity and cannot be identified as principal in an IAM policy.
    + use groups to assigns permissions to the users.
    + always assign the least priviledges when assigning permissions.

- **IAM ROLES**: Think of it as assigning access to the `AWS` services such as you might set a role for `DynamoDB` to readonly.
    + They are created and then assumed by trusted entities and define a set of permissions for making `AWS` requests.
    + with roles you can delegate permissions to resources for users and services without using a permanent credentials.
    + `AWS` users or services can assume a role to obtain temporary security crendentials that can used to make `aws` api calls.
    + 

- **IAM Policies**: They are documents that defines the permissions and can be applied to users,groups and roles.
    + Policy documents are written in `json`.
    + All permissions are implicitly denied by default.
    + the most restrictive policy is applied.
    + The `IAM` policy simulator is a tool that helps you understand,test and validate the effects of access controls policies.