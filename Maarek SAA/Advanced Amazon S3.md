#amazon_s3 

### **S3 Lifecycle Rules (with S3 Analytics)**

- **Lifecycle Rules**:
    - Automate the **transition or expiration** of objects across different **storage classes**.
    - Common transitions:
        - **Move to Standard-IA/One Zone-IA** after a set time for infrequent access.
        - **Move to Glacier/Deep Archive** for long-term archival.
        - **Expire objects** by automatically deleting them after a certain period.
- **S3 Analytics**:
    - Provides **insights into object access patterns** to optimize lifecycle rules.
    - Helps determine when to transition objects to lower-cost storage classes.

---

### **S3 Requester Pays**

- **Requester Pays Buckets**:
    - **Requester** is charged for **data transfer and request fees** instead of the bucket owner.
    - Use Case: **Public datasets** where multiple users need access, such as open government data.
    - Requires clients to specify `"x-amz-request-payer: requester"` in requests.

---

### **S3 Event Notifications**

- **Event Notifications**:
    - Automatically trigger **notifications or actions** when specific **bucket events** occur.
    - Supported events:
        - **PUT** (object created)
        - **DELETE** (object deleted)
        - **COPY** (object copied)
    - Notification Targets:
        - **Amazon SQS**: Send messages to a queue.
        - **Amazon SNS**: Broadcast notifications to subscribers.
        - **AWS Lambda**: Trigger functions to process objects in real-time.
    - Use Case: Automating workflows, such as triggering data processing after upload.

---

### **S3 Performance**

- **Performance Features**:
    - **Prefix Partitioning**: Improves throughput by distributing objects across multiple partitions.
    - **Parallel Uploads**: Use **multipart upload** for faster uploads of large files.
    - **S3 Transfer Acceleration**: Uses **CloudFront edge locations** to speed up uploads over long distances.
    - **Read-after-write consistency** for PUTs of new objects.
    - **Eventual consistency** for overwrite operations.

---

### **S3 Batch Operations**

- **S3 Batch Operations**:
    - Perform large-scale operations on multiple objects **across a bucket**.
    - Operations include:
        - **Copying objects**.
        - **Modifying object tags or access control lists (ACLs)**.
        - **Running Lambda functions** on objects.
    - **Manifest files** specify the list of objects to act upon.
    - Use Case: Large-scale management or updates of object metadata and properties.

---

### **S3 Storage Lens**

- **S3 Storage Lens**:
    - Provides **visibility into storage usage and activity** across all buckets.
    - **Metrics & Insights**:
        - Total storage size, object counts, storage class breakdowns.
        - Identify **inactive data** and optimize **cost-efficiency**.
    - Supports **dashboards** with detailed visualizations and reports.
    - Use Case: **Analyze trends, find anomalies**, and improve storage policies.

---

### **Other Important Concepts**

- **S3 Object Lock**:
    - **WORM (Write Once Read Many)** feature to prevent deletion or modification of critical data.
    - Use Case: Regulatory compliance (e.g., financial records).
- **MFA Delete**:
    - Requires **multi-factor authentication** to delete objects or versions, enhancing security.
- **S3 Access Points**:
    - Create **custom access endpoints** for specific applications or users.
    - Simplifies management by isolating access to **specific datasets** within a bucket.
- **Replication Time Control (RTC)**:
    - Guarantees replication of objects to the destination bucket **within 15 minutes**.