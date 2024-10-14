#route_53

### **DNS (Domain Name System)**

- **DNS**: Translates domain names (e.g., example.com) into IP addresses to direct traffic to the appropriate servers.
- **DNS Records**:
    - **A record**: Maps a domain name to an IPv4 address.
    - **AAAA record**: Maps a domain name to an IPv6 address.
    - **CNAME**: Maps a domain name to another domain name (used for redirection).
    - **MX record**: Directs email to mail servers.
    - **TXT record**: Stores text-based information (e.g., for domain verification).
    - **NS (Name Server) record**: Points to the authoritative DNS server for a domain.

### **Route 53 Overview**

- **AWS Route 53**: A scalable and highly available **DNS web service**. It connects user requests to infrastructure hosted on AWS (like EC2, S3, and ELB) and outside AWS.
- **Features**:
    - **Domain Registration**: Allows buying and managing domain names.
    - **DNS Management**: Hosts and resolves DNS records.
    - **Health Checks**: Monitors the health of endpoints and services (ensures only healthy endpoints are used for routing).
    - **Traffic Flow**: Automates routing based on policies (helps manage complex routing requirements).
    - **Hosted Zones**: A container for DNS records; can be **Public** (visible on the internet) or **Private** (used within VPC).

### **Routing Policies**

- **Simple Routing Policy**:
    - Default routing; one DNS response per query (no complex rules).
    - **Use Case**: Single web server or service endpoint.
- **Weighted Routing Policy**:
    - Distributes traffic across multiple resources based on **assigned weights**.
    - **Use Case**: Distribute load or perform A/B testing.
- **Latency Routing Policy**:
    - Routes traffic based on **lowest latency** between users and AWS regions.
    - **Use Case**: Improve user experience by minimizing response time.
- **Failover Routing Policy**:
    - Directs traffic to a **primary resource** and switches to a **backup** when the primary is unhealthy.
    - **Use Case**: Ensure high availability.
- **Geolocation Routing Policy**:
    - Routes traffic based on the **user’s geographic location**.
    - **Use Case**: Serve region-specific content or comply with legal requirements.
- **Geoproximity Routing Policy**:
    - Routes traffic based on a resource’s **location and configured bias** to influence traffic flow.
    - **Use Case**: Control traffic distribution to nearby regions or skew traffic intentionally.
- **Multivalue Answer Policy**:
    - Provides **multiple IP addresses** in response to a DNS query. Route 53 chooses healthy resources.
    - **Use Case**: Load balancing or redundancy.
### **Health Checks and Monitoring**

- **Health Checks**:
    - Monitor the **availability** and **performance** of endpoints.
    - Integrated with CloudWatch for **alarms and metrics**.
- **Failover Scenarios**: If a primary endpoint fails, Route 53 reroutes traffic to a healthy backup.

### **Key Concepts and Exam Tips**

- **Hosted Zone**: Links domain names to specific resources.
- **TTL (Time to Live)**: Controls how long a DNS resolver caches information. Lower TTLs ensure faster updates but increase query load.
- **Alias Records**: Special Route 53 records that work like CNAME but can map to AWS resources like **ELB** and **S3** buckets directly.
- **Private DNS**: Route 53 can be used to host private DNS within a **VPC** to resolve internal resources.