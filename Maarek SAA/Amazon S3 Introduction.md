#amazon_s3

### **S3 Overview**

- **Amazon S3 (Simple Storage Service)**:
    - **Object storage** service with high scalability, availability, and durability.
    - Stores **data as objects** within **buckets** (containers for objects).
    - Supports **virtually unlimited storage** and high performance.
    - **Objects** contain:
        - **Data** (file or binary).
        - **Metadata** (information about the object).
        - **Unique key** (identifier within a bucket).

---

### **Buckets**

- **Buckets**:
    - Containers that store **objects** (e.g., files, images, videos).
    - Each bucket must have a **globally unique name** across AWS.
    - **Bucket-level operations**:
        - Set **permissions** using bucket policies or ACLs.
        - Define **versioning** and **replication** settings.
    - Buckets are tied to a **specific region**, but objects within can be accessed globally (if permissions allow).
- **Naming Requirements**:
    - Must use **DNS-compliant names** (lowercase, no special characters).
    - Cannot use names resembling **IP addresses** (e.g., 192.168.1.1).

---

### **Objects**

- **Objects**:
    - Basic unit of storage in S3 (e.g., a document, image, video).
    - Each object consists of **data, metadata**, and a **unique key**.
    - Objects are immutable—updating an object creates a **new version** (if versioning is enabled).
- **Object Size**:
    - **Maximum size**: 5 TB per object.
    - **Multipart upload** required for objects larger than 5 GB.
- **Accessing Objects**:
    - Objects can be accessed via **REST APIs** or **pre-signed URLs** (temporary access).

---

### **S3 Security: Bucket Policy**

- **Bucket Policies**:
    - **JSON-based policies** that define access permissions at the bucket level.
    - Used to **allow or deny access** to users, services, or IP ranges.
- **Security Features**:
    - **IAM Policies**: Grant access to users and roles.
    - **Access Control Lists (ACLs)**: Legacy method, less recommended.
    - **MFA Delete**: Requires multi-factor authentication to delete objects or versions.
    - **Bucket Block Public Access**: Prevents unintended public exposure.
    - **Encryption**:
        - **SSE (Server-Side Encryption)**: Automatically encrypts data at rest.
        - **Client-Side Encryption**: Data is encrypted before being uploaded.

---

### **S3 Website Overview**

- **S3 Static Website Hosting**:
    - Enables hosting of **static websites** (HTML, CSS, JS) directly on S3.
    - **Index Document**: Main entry page (e.g., `index.html`).
    - **Error Document**: Fallback page (e.g., `404.html`).
    - **Public Access**: Bucket policy must allow public reads.
    - **Use Case**: Simple websites or documentation sites.

---

### **S3 Versioning**

- **Versioning**:
    - Keeps multiple versions of objects in a bucket.
    - Protects against **accidental deletions or overwrites**.
- **Behavior**:
    - Deleting an object adds a **delete marker** without removing previous versions.
    - Versioning can be **suspended**, but existing versions remain.
- **MFA Delete**: Enhances security by requiring MFA to delete object versions.

---

### **S3 Replication**

- **Replication**:
    - Automatically copies objects from one bucket to another.
    - **Types**:
        - **Cross-Region Replication (CRR)**: Copies objects to a different region.
        - **Same-Region Replication (SRR)**: Copies objects within the same region.
- **Requirements**:
    - Both source and destination buckets must have **versioning** enabled.
- **Use Cases**:
    - Disaster recovery, compliance, and data redundancy.

---

### **S3 Storage Classes Overview**

- **Storage Classes**:
    - Provide different options for **availability, performance, and cost**.
- **Standard**:
    - General-purpose storage with **99.99% availability** and 11 9s durability.
- **Intelligent-Tiering**:
    - Optimizes cost by automatically moving objects between frequent and infrequent tiers.
- **Standard-IA (Infrequent Access)**:
    - For data accessed occasionally, with **retrieval fees**.
- **One Zone-IA**:
    - Same as Standard-IA, but data is stored in **one availability zone**.
- **Glacier**:
    - Archival storage with retrieval times from **minutes to hours**.
- **Glacier Deep Archive**:
    - **Lowest cost** storage for cold data, with **12-48 hour** retrieval times.