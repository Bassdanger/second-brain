1) create VPC, subnet (unique CIDR), ssh (for bastion host), icmp (source range should be partners CIDR) FW rules  
  
2) create a VM, put it in the new VPC, NO EXTERNAL IP is needed,  and share internal IP with partner  
  
3) go to Network Connectivity menu then VPN then classic VPN  
  
4) VPN gateway:  
add settings, put it in your region that you choose, create static ip address and record it  
(only your info goes here)  
  
5) tunnel settings: *one partner* generates IKE secret and shares it, It must be the same for both.  
Remote peer IP address: your partner's static IP  
IKE version: v2  
Choose route based tunnel and for "Remote network IP ranges" add partners subnet CIDR range  
  
tear down:  
- delete tunnel  
- delete cloud vpn gateway  
- release static ip (in VPC menu)  
- delete vm  
- delete vpc (if you created one for today)