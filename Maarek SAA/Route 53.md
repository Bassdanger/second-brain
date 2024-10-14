### **DNS (Domain Name System)**

- **DNS**: Converts domain names (e.g., example.com) to IP addresses to connect users to servers or resources.
- **DNS Records**:
    - **A Record**: Maps a domain to an IPv4 address.
    - **AAAA Record**: Maps a domain to an IPv6 address.
    - **CNAME Record**: Points one domain to another domain name.
    - **MX Record**: Directs emails to mail servers.
    - **NS (Name Server) Record**: Points to authoritative DNS servers for the domain.
    - **TXT Record**: Stores text for verification or other metadata.

---

### **Route 53 Overview**

- **Route 53**: AWS’s scalable and highly available **DNS web service** for both internal and external DNS.
- **Functions**:
    - **Domain Registration**: Buy and manage domain names directly within AWS.
    - **DNS Hosting**: Manages records via **Hosted Zones** (public or private).
    - **Traffic Management**: Routes user requests across resources globally using **Routing Policies**.
    - **Health Checks & Failover**: Monitors endpoint health and ensures traffic flows to healthy endpoints.
- **Hosted Zones**: Containers for DNS records.
    - **Public Hosted Zone**: Available on the internet.
    - **Private Hosted Zone**: Used within a **VPC** for internal services.

---

### **Registering a Domain in Route 53**

- Domains can be purchased directly in **Route 53**.
- Route 53 creates a **Hosted Zone** with relevant DNS records when registering a domain.
- Supports **automatic renewal** of domains to prevent expiration.

---

### **Time to Live (TTL)**

- **TTL**: Defines how long a DNS record is cached by DNS resolvers.
- **Lower TTLs**: Faster DNS updates but higher query traffic.
- **Higher TTLs**: Less traffic but slower propagation of changes.

---

### **CNAME vs Alias Records**

- **CNAME Record**:
    
    - Maps one domain name to another (e.g., [www.example.com](http://www.example.com) -> example.com).
    - Cannot be used at the **root domain** (e.g., example.com).
- **Alias Record**:
    
    - Works similarly to **CNAME** but can point to AWS services like **S3 buckets, CloudFront, and ELB**.
    - **Supports root domain** (e.g., example.com).
    - **Free** DNS queries within AWS (unlike CNAME queries).

---

### **Routing Policies**

- **Simple Routing Policy**:
    
    - One DNS response per query without complex rules.
    - **Use Case**: Single resource or service.
- **Weighted Routing Policy**:
    
    - Distributes traffic based on **assigned weights** (e.g., 70-30 split).
    - **Use Case**: Load distribution or testing.
- **Latency Routing Policy**:
    
    - Routes based on **lowest network latency** to improve user experience.
    - **Use Case**: Directing users to the closest AWS region.
- **Failover Routing Policy**:
    
    - Routes traffic to a **primary resource**; switches to a **backup** if the primary fails.
    - **Use Case**: High availability.
- **Geolocation Routing Policy**:
    
    - Routes traffic based on the **user’s location**.
    - **Use Case**: Legal compliance or region-specific content.
- **Geoproximity Routing Policy**:
    
    - Routes traffic based on **proximity** and can be skewed using a **bias** value.
    - **Use Case**: Control distribution near a specific region.
- **Multivalue Answer Policy**:
    
    - Provides **multiple IP addresses**; Route 53 selects healthy ones.
    - **Use Case**: Basic load balancing and redundancy.

---

### **Health Checks**

- **Purpose**: Ensure traffic is routed only to healthy endpoints.
- **Monitoring Types**:
    - HTTP/HTTPS endpoint checks.
    - TCP-based health checks.
    - Can monitor **CloudWatch Alarms** for custom metrics.
- **Failover Support**: Automatically shifts traffic to healthy resources when failures occur.
- Can trigger **CloudWatch alarms** for proactive alerting.

---

### **3rd-Party Domains & Route 53**

- Route 53 supports **external domains** registered through other providers.
- To use Route 53 for DNS management, update the **NS records** at the 3rd-party registrar to point to the **Route 53 name servers**.
- **Alias Records** can still be used to route to AWS services even with external domains.

---

### **Key Exam Concepts**

- **Alias Records** vs. **CNAME**: Use Alias for AWS services and root domains.
- **TTL** management is crucial for balancing DNS update speed and query traffic.
- **Private Hosted Zones**: Used within VPCs to resolve private resources.
- **Health Checks**: Essential for failover routing.
- **Multiple Routing Policies**: Can combine policies (e.g., weighted + failover).
- **Geolocation** vs. **Geoproximity**: Geolocation focuses on user location, while geoproximity allows traffic biasing.