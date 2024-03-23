# To login to EC2 using SSM manager without having any SSH keypair or public IP.

1. Create an EC2 instance without any public IP or SSH key pair.
2. Update under EC2- Actions->Security->Modify IAM role
3. We will get the below error.
![image](https://github.com/Abinash04/AWS-hands-on-labs/assets/15240069/65aeaec9-950f-412f-8a9c-afd0bb27979c)
4. Lets fix this.

Attempt:
1. Removed all security group having inbound and outbound rules which was present. -didnt work
2. Need to enable outbound rules in the security group with TCP 443 port. - this worked.
   Network setting:
Network- default
Subnet- No preference
Public IP - Enabled
security group - default
3. Tried below setting - Didnt work
   Network- default
Subnet- No preference
Public IP - Disabled
security group - default

Reference:
https://www.youtube.com/watch?v=3tKB947rT5Q
