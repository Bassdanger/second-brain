#amazon_s3

### **S3 Overview**

- **Amazon S3 (Simple Storage Service)**:
    - Object storage service offering **scalable, durable, and available** cloud storage.
    - Stores **objects** (files) within **buckets** (containers).
    - Objects consist of **data, metadata**, and a **unique key**.
    - Use cases: Data backups, static website hosting, data lakes, and content delivery.

---

### **Buckets**

- **Buckets**:
    - Containers for **storing objects**.
    - Each bucket has a **unique global name** and resides in a **specific AWS region**.
    - Bucket configurations include **policies, versioning, replication**, and **access controls**.
    - **Naming Rules**:
        - Must be **DNS-compliant** (lowercase, no special characters).
        - Cannot resemble **IP addresses** (e.g., 192.168.1.1).

---

### **Objects**

- **Objects**:
    - Data stored in S3, consisting of:
        - **Content** (actual file or data).
        - **Metadata** (information like size, content type, or custom tags).
        - **Key**: A unique identifier for the object within the bucket.
    - **Max size**: 5 TB; objects larger than 5 GB require **multipart upload**.
    - Objects are **immutable**—updating creates a new version (if versioning is enabled).

---

### **S3 Security: Bucket Policy**

- **Bucket Policies**:
    - JSON-based policies to **control access** at the bucket level.
    - Can restrict or allow access for **users, roles, IP ranges, or services**.
- **Additional Security Features**:
    - **IAM Policies**: Grant access to specific users or roles.
    - **Access Control Lists (ACLs)**: Legacy method, less recommended.
    - **Encryption**: Server-side (SSE) or client-side encryption available.
    - **MFA Delete**: Requires **multi-factor authentication** to delete versions.
    - **Block Public Access**: Prevents public exposure of sensitive data.

---

### **S3 Website Overview**

- **S3 Static Website Hosting**:
    - Allows hosting of **static websites** (HTML, CSS, JavaScript) on S3.
    - Requires:
        - **Public read access** enabled via bucket policy.
        - An **index document** (e.g., `index.html`) and optional **error document** (e.g., `404.html`).
    - **Use Case**: Hosting simple websites or documentation with minimal configuration.

---

### **S3 Versioning**

- **Versioning**:
    - Stores **multiple versions** of the same object in a bucket.
    - Protects against **accidental overwrites or deletions**.
    - **MFA Delete**: Requires MFA for critical deletion operations.
    - **Behavior**:
        - **Suspending versioning** keeps old versions but prevents new ones from being created.
        - Deleting objects adds a **delete marker** without removing prior versions.

---

### **S3 Replication**

- **Replication**:
    - Automatically copies objects between buckets.
    - **Types**:
        - **Cross-Region Replication (CRR)**: Copies to a different AWS region.
        - **Same-Region Replication (SRR)**: Copies within the same region.
    - Requirements:
        - **Versioning** must be enabled on both source and destination buckets.
        - Appropriate **IAM roles** must be configured.
    - **Use Cases**: Disaster recovery, compliance, redundancy, and data separation.

---

### **S3 Storage Classes Overview**

- **S3 Storage Classes**: Offer varying levels of **performance, availability, and cost** based on access patterns.

#### 1. **S3 Standard**

- **General-purpose** storage for frequently accessed data.
- **Availability**: 99.99%
- **Durability**: 11 9s (99.999999999%).
- **Use Case**: Active workloads (e.g., websites, applications).

#### 2. **S3 Intelligent-Tiering**

- Automatically moves data between **frequent** and **infrequent access tiers** based on usage.
- **No retrieval fees**; ideal for unpredictable access patterns.
- Use Case: Dynamic workloads with changing access requirements.

#### 3. **S3 Standard-IA (Infrequent Access)**

- Lower cost for data that is accessed **infrequently** but requires rapid access when needed.
- **Availability**: 99.9%
- **Retrieval fees** apply.
- Use Case: Backups, disaster recovery.

#### 4. **S3 One Zone-IA**

- Same as **Standard-IA**, but stores data in a **single availability zone**.
- **Lower cost** but reduced fault tolerance.
- Use Case: Data that can tolerate some downtime (e.g., non-critical backups).

#### 5. **S3 Glacier**

- **Archival storage** for long-term backups and compliance data.
- Retrieval times range from **minutes to hours**.
- Use Case: Data that is rarely accessed but must be retained (e.g., legal records).

#### 6. **S3 Glacier Deep Archive**

- **Lowest-cost** storage option for cold data.
- Retrieval times: **12 to 48 hours**.
- Use Case: Long-term archival data (e.g., historical records, regulatory data).