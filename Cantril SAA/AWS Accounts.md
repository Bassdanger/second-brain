#aws_accounts #root_user #aws_root_user

- `AWS Account` - a container for identities (users) and Resources
- `Account Root User` - unique to each AWS Account
	- Has full control of the AWS Account and of any resources created
	- Can't be restricted
- Resources bill to the AWS Account payment method as they are consumed
- `Identity and Access Managment (IAM)` - Users, Groups, and Roles can be created and given full or limited permissions
- AWS Accounts can contain the impact of admin errors, bad actors. You can use separate accounts for separate things like a DEV, PROD,TEST.
- By default all access to an AWS Account is denied besides the Account Root User.