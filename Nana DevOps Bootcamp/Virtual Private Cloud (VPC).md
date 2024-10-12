#vpc 

-  VPC for each Region
- VPC is your own isolated network in the cloud
- VPC spans all the AZs (Subnets) in that Region
- Multiple VPCs in different Regions
- Virtual representation of network infrastructure
- Setup of servers, network configuration moved to cloud
- Your components have to run in a VPC
- Subnet
	- Subnet for each AZ
	- Private network inside a network
	- Private and Public Subnets
	- Firewall Rule configuration makes it either a private and/or public subnet
- Controlling Access
	- Internet Gateway connects the VPC to the outside internet
	- Secure your components
	- Controls access to your VPC
	- Control access to your individual server instances
- Security
	- Configure access on subnet level => NACL
	- Configure access on instance level => Security Group
	- Create on VPC level and assign to subnet and instance