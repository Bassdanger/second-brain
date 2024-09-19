#aws_security_groups #aws_classic_ports #security_groups

- Security Groups are the fundamental of network security in AWS
- They control how traffic is allowed into or out of our EC2 instances 
- only contain allow rules
- rules can reference by IP or by a security group
- ![[Pasted image 20240917192255.png]]
- are acting as a "firewall" on EC2 instances
- They regulate:
	- Access to Ports
	- Authorized IP ranges - IPv4 and IPv6
	- Control of inbound network (from other to the instance)
	- Control of outbound network (from the instance to other)
	- ![[Pasted image 20240917192458.png]]
- ![[Pasted image 20240917192635.png]]
- Can be attached to multiple instances
- Locked down to region/VPC combination
- Live outside the EC2, if traffic is blocked EC2 instance won't see it
- It's good to maintain one separate security group for SSH access
- if application is not accessible (time out), security group error
- If application says connection refused error, application error or not launched
- All inbound traffic is blocked by default
- All outbound traffic is authorized by default
- ![[Pasted image 20240917193136.png]]
- Classic Ports to know
	- `22` = SSH (Secure Shell) - log into a Linux instance
	- `21` = FTP (File Transfer Protocol) - upload files into a file share
	- `22` = SFTP (Secure File Transfer Protocol) - upload files using SSH
	- `80` = HTTP - access unsecured websites
	- `443` = HTTPS - access secured websites
	- `3389` = RDP (Remote Desktop Protocol) - log into a Windows instance