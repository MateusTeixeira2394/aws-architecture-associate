# 1. Amazon Aurora ☁️🛢️

**Amazon Aurora** is a fully managed, high-performance relational database engine that is designed for high availability and scalability. It is part of the Amazon Relational Database Service (RDS) and is compatible with both MySQL and PostgreSQL, offering the performance and availability of commercial databases at a lower cost.

## 1.1. Key Features of Amazon Aurora:

1. **High Performance**:
   - Aurora delivers up to five times the performance of standard MySQL and up to three times the performance of standard PostgreSQL databases, thanks to its underlying architecture designed for low-latency read and write operations.
   
2. **MySQL and PostgreSQL Compatibility**:
   - Aurora is compatible with both MySQL and PostgreSQL, allowing applications built for these databases to easily migrate to or use Aurora without major changes to code or tools.

3. **High Availability and Durability**:
   - Aurora automatically replicates your data across multiple Availability Zones (AZs), ensuring high availability. It provides automatic failover in case of an outage, and your data is always replicated across multiple copies.
   - Aurora also performs continuous backups to Amazon S3, with point-in-time recovery to restore data from any point within the backup retention period.

4. **Scalability**:
   - Aurora can automatically scale both storage and compute resources. It can grow storage size as needed, from as little as 10 GB to up to 128 TB per database instance.
   - Aurora also supports read replicas, allowing you to scale out read-heavy workloads by distributing traffic across multiple replicas.

5. **Fault-Tolerant and Self-Healing Storage**:
   - Aurora’s storage is designed to be fault-tolerant, meaning it can handle disk failures without affecting database operations. Aurora continuously scans for errors in data blocks and automatically repairs them using the correct data from other copies.

6. **Global Database**:
   - Aurora Global Database allows you to deploy a single Aurora database across multiple AWS regions, improving performance and availability for globally distributed applications.

7. **Serverless Option**:
   - Aurora offers a **serverless** option, where the database automatically adjusts its capacity based on application needs. This is particularly useful for workloads that have unpredictable or intermittent traffic.

8. **Security**:
   - Aurora integrates with AWS Identity and Access Management (IAM), AWS Key Management Service (KMS), and AWS Secrets Manager to provide strong security controls. It supports encryption at rest and in transit.

9. **Cost-Effective**:
   - Aurora offers a pay-as-you-go model, and its costs are lower than traditional commercial databases. You only pay for the resources you use, and there are no upfront costs.

## 1.2. Use Cases for Amazon Aurora:

1. **High-Performance Applications**:
   - Applications requiring high throughput and low latency, such as online transaction processing (OLTP) systems, e-commerce platforms, or financial services applications, benefit from Aurora's performance optimizations.

2. **Scaling Read-Intensive Workloads**:
   - Applications that need to handle large volumes of read requests, like content management systems or social media platforms, can use Aurora’s read replicas to scale.

3. **Enterprise Applications**:
   - Aurora is ideal for enterprises migrating from commercial databases (like Oracle or SQL Server) to a more cost-effective, cloud-native solution that doesn’t compromise on performance or availability.

4. **Serverless Workloads**:
   - Applications with variable or unpredictable workloads, such as development environments or event-driven applications, can leverage Aurora Serverless to automatically scale up and down without manual intervention.

5. **Global Applications**:
   - Aurora Global Database is well-suited for globally distributed applications that need low-latency access to data from multiple regions.

## 1.3. Conclusion:

Amazon Aurora is a powerful, fully managed relational database that combines the performance, availability, and durability of commercial databases with the cost-effectiveness and flexibility of open-source engines like MySQL and PostgreSQL. Its scalability, fault tolerance, and security features make it a great choice for high-performance applications, mission-critical systems, and globally distributed workloads.

## 1.4. Summary

- Started in 2014
- Aws is owner
- Mysql compatible
- 5x faster than mysql and 3x faster than postgres
- 10x cheaper
- 10GB default
- Auto-scaling with 64Gb default
- Maximum 64TB
- It is possible to create until 15 replica
  - The **main process** handles database **writing** and each **replica** handles **reading**
  - You can configure to many applications read the database using some replica without affecting the main process of the database
- Recover: point in-time
- Continuous backup: until 3 zones
- Free tier is not available
