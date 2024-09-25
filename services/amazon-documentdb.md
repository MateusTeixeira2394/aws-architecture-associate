# 1. Amazon DocumentDB 📄☁️

Amazon **DocumentDB** (with MongoDB compatibility) is a fully managed, scalable, and highly available document database service designed to support large-scale MongoDB workloads. It is optimized for JSON-like document storage and provides the same API and query language as MongoDB, making it easy for developers to migrate and run MongoDB workloads in the AWS cloud without managing the database infrastructure.

## 1.1. Key features

- **MongoDB Compatibility:**
    - **Purpose:** Amazon DocumentDB is compatible with MongoDB 3.6 and later versions, allowing applications using MongoDB drivers and tools to interact with the database seamlessly.
    - **Query Support:** Supports MongoDB APIs, BSON data format, and MongoDB aggregation framework, providing rich querying capabilities similar to MongoDB.

- **Fully Managed:**
    - **Purpose:** As a managed service, Amazon DocumentDB automatically handles tasks such as provisioning, patching, backups, and scaling, freeing developers from managing the infrastructure.
    - **Backup and Restore:** Offers continuous backups to Amazon S3 and point-in-time recovery options.

- **Scalability:**
    - **Storage Auto-Scaling:** Automatically scales storage up to 64 TB as the size of your data grows, without affecting application performance.
    - **Read Scalability:** Allows for up to 15 low-latency read replicas, which can handle millions of read requests per second.

- **High Availability:**

    - **Multi-AZ Deployments:** Amazon DocumentDB supports multi-AZ deployments, ensuring that the database remains highly available and fault-tolerant. It can automatically fail over to a standby instance in case of an issue with the primary instance.

- **Performance:**
    - Designed to be fast and optimized for high-volume reads, offering low-latency access to document data with the ability to scale read capacity horizontally.
    - Performance can be optimized through provisioned capacity and elastic scaling for both reads and writes.

- **Security:**
    - **Encryption:** Amazon DocumentDB supports encryption at rest using AWS Key Management Service (KMS) and encryption in transit using TLS.
    - **VPC Integration:** Can be launched within an Amazon VPC, allowing you to isolate your database from the public internet and control access through security groups.

- **Monitoring and Management:**
    - Integrates with Amazon CloudWatch for monitoring performance metrics such as CPU utilization, memory usage, disk space, and query performance.
    - Provides automated backups, retention policies, and point-in-time restores.

- **Migration Tools:**
    - Amazon Database Migration Service (DMS) allows for the easy migration of MongoDB workloads to Amazon DocumentDB without downtime.

## 1.2. Summary

Amazon DocumentDB is a fully managed document database service built for MongoDB workloads, offering high performance, scalability, and flexibility for applications that need document-based storage. It is ideal for content management, real-time analytics, and other document-centric use cases, providing a fully managed environment with MongoDB compatibility to simplify operations.