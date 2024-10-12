#networking 

- LAN
	- Local Area network
	- Collection of devices connected together in one physical location
	- Each device has a unique IP address
	- Devices communicate via IP addresses
- IP 
	- 32 bit value
	- 1 bit = 1 or 0
- Switch
	- Sits within the LAN
	- Facilitates the connection between all the devices within the LAN
- Router
	- Sits between LAN and outside networks (WAN)
	- WAN = Wide Area network
	- Connects devices on LAN and WAN
	- Allows networked devices to access the Internet
	- Gateway = IP address of Router
- Subnet
	- Devices in the LAN belong to same IP address range
	- Subnet = logical subdivision of an IP network
	- Subnetting = process of dividing a network into two or more networks
	- Example of IP address range: 192.168.0.0 255.255.255.0
		- First is Starting point of IP range, the first IP in the range
		- Sets the IP range
	- 255.255.0.0 - means that 16 bits are fixed
	- 255.255.255.0 - means 24 bits are fixed
- CIDR Block
	- Subnet Mask dictates how many bits are fixed
	- CIDR = Classless Inter-Domain Routing
	- 192.168.0.0/16 or 192.168.0.0/24
	- /16 bits are fixed /24 bits are fixed
- Any device needs 3 pieces of data for communication
	- IP Address
	- Subnet
	- Gateway
- NAT
	- IP Address range chosen by an administrator
	- Each device gets a unique IP from that range
	- IP address within LAN are not visible to the outside network or internet
	- Your Laptop's private IP address is replaced by the router
		- Network Address Translation
	- key functionality of a router
	- Benefits of NAT:
		- Security and Protection of devices within LAN
		- Reuse IP addresses
		- Same IP address range within their LAN is OK
	- Limited number of IPv4 addresses available
- Firewall
	- By default, the server is not accessible from outside the LAN
	- A system that prevents unauthorized access from entering a private network
	- Using Firewall Rules you can define, which requests are allowed
	- Firewall Rules
		- Which IP address in your network is accessible
		- Which IP address can access your server
- Port
	- Every device has a set of ports
	- You allow specific ports (door)
	- You can allow specific ports (doors) AND specific IP address (guests)
	- Different applications listen on specific ports
	- Standard ports for many applications
	- Port 80: Web Servers
	- Port 3306: MySQL
	- Port: 5432
	- For every application you need a port
	- Each port is unique on a device
	- allows device IP address at port to be accessed
		- Port Forwarding
- Domain Name System (DNS)
	- Why do we use names instead of IP addresses?
		- Humans are better at remembering words and names instead of numbers
	- Mapping IP addresses to Names
	- DNS = translates domain names to IP addresses
	- Domain Names have a hierarchical structure
		- Root Domains
			- .
		- Top Level Domains
			- .com, .edu, .net etc
	- Regulated by ICANN
		- Authorizes Domain Name Registrars, which register and assign domain names
	- Subdomains
		- Example: www.courses.techworld-with-nana.com
		- courses added
	- DNS Resolution
		- DNS names are cached for efficiency
	- Networking Commands
		- `ipconfig`
		- `netstat`
		- `ps aux`
		- `nslookup`
		- `ping`
			- Can use these to Troubleshoot your network