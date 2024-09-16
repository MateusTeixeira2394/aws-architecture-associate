# 1. Introduction 🚩

Amazon **Relational Database Service (RDS)** is a managed service provided by AWS that makes it easy to set up, operate, and scale a relational database in the cloud. It automates time-consuming tasks such as hardware provisioning, database setup, patching, and backups, allowing you to focus on your applications.

# 2. Supported SQL Databases 💿

RDS supports several popular database engines, including:

- Amazon Aurora (a MySQL and PostgreSQL-compatible relational database)
- MySQL
- PostgreSQL
- MariaDB
- Oracle Database
- Microsoft SQL Server

## 2.1. Comparison

Bellow, follows the comparison of the databases available at the moment that this document has been written:

| **Database Engine**                     | **Compatibility**                                      | **Performance**                                          | **Scalability**                                               | **Replication**                                           | **Storage**                            | **Use Case**                                                                             |
| --------------------------------------- | ------------------------------------------------------ | -------------------------------------------------------- | ------------------------------------------------------------- | --------------------------------------------------------- | -------------------------------------- | ---------------------------------------------------------------------------------------- |
| **Amazon Aurora MySQL-Compatible**      | MySQL-compatible                                       | Up to 5x faster than standard MySQL                      | Automatically scales up to 128 TB per instance                | Up to 15 read replicas, multi-region replication          | Automatically grows up to 128 TB       | Applications needing MySQL compatibility with better performance and scalability         |
| **Amazon Aurora PostgreSQL-Compatible** | PostgreSQL-compatible                                  | Up to 3x faster than standard PostgreSQL                 | Automatically scales up to 128 TB per instance                | Up to 15 read replicas, multi-region replication          | Automatically grows up to 128 TB       | Applications needing PostgreSQL compatibility with enhanced performance                  |
| **MySQL**                               | Broad compatibility                                    | Suitable for web applications, slower than Aurora        | Handles moderate workloads, manual sharding for large scale   | Up to 5 read replicas                                     | Up to 64 TB depending on instance type | Small to medium-sized web applications                                                   |
| **PostgreSQL**                          | Standards compliance, extensibility                    | Slower than MySQL but offers advanced features           | Manages large workloads, less optimized than Aurora           | Up to 5 read replicas                                     | Up to 64 TB depending on instance type | Applications requiring complex queries and data integrity                                |
| **MariaDB**                             | Drop-in replacement for MySQL                          | Similar to MySQL with some enhancements                  | Comparable to MySQL, requires manual sharding for large scale | Up to 5 read replicas                                     | Up to 64 TB depending on instance type | Alternative to MySQL with more open-source transparency                                  |
| **Microsoft SQL Server**                | Enterprise-grade, Windows-based environments           | High performance, especially for transactional workloads | Can handle large-scale applications, more complex scaling     | Transactional replication, Always On availability groups  | Up to 16 TB depending on instance type | Enterprise applications, especially within Microsoft ecosystem                           |
| **Oracle Database**                     | Enterprise-grade, advanced features for enterprise use | High performance in large-scale, mission-critical apps   | Excellent scalability, though complex                         | Data Guard, Active Data Guard, GoldenGate for replication | Up to 64 TB depending on instance type | Enterprise-grade applications requiring advanced features, data security, and compliance |

# 3. Multi-AZ x Read Replica 📈

## 3.1. Multi-AZ

**Multi-AZ** (Multiple Availability Zone) deployments provide high availability and failover support for DB instances. Here’s how it works:

- **Primary and Standby Instances**: When you create a Multi-AZ deployment, Amazon RDS automatically provisions and maintains a synchronous standby replica in a different Availability Zone (AZ). This replica is not directly accessible; it’s used for failover purposes.
- **Automatic Failover**: In the event of a failure (e.g., hardware failure, AZ outage), Amazon RDS automatically fails over to the standby replica to minimize downtime. The failover process is seamless and usually takes a few minutes.
- **Data Durability**: Multi-AZ deployments ensure that your data is replicated to the standby instance, providing durability and protection against data loss.

**Use Case**: Multi-AZ deployments are ideal for production databases where high availability and data durability are critical.

**Endpoint**: It uses a single DNS endpoint to connect to your RDS instance. This endpoint remains constant from the perspective of your application.

## 3.2. Read Replicas

**Read Replicas** are used to scale out read-heavy database workloads. They provide a way to offload read traffic from the primary database. Here’s how it works:

- **Asynchronous Replication**: Read Replicas use asynchronous replication to copy data from the primary database to one or more replica instances. This means there may be a slight delay between the primary database and the replicas.
- **Scaling Reads**: You can distribute read traffic across multiple Read Replicas to improve performance and reduce load on the primary instance.
- **Read-Only**: Read Replicas are read-only, meaning they cannot handle write operations. They are used solely for read queries.

**Use Case**: Read Replicas are useful for applications with heavy read workloads where scaling out read operations can help improve performance.

**Manual Setup**: Creating and managing Read Replicas involves manual setup. You specify which primary instance you want to replicate and how many replicas you want.

**Endpoint**: RDS instance has its own endpoint.

## 3.3. Summary

- **Multi-AZ**: Provides high availability and failover support by maintaining a synchronous standby replica in a different AZ. Best for critical production databases where uptime is crucial.
- **Read Replicas**: Improve read performance and scalability by asynchronously replicating data to one or more read-only instances. Best for applications with high read traffic.

You can use both features together to achieve high availability, data durability, and improved read performance.

# 4. Backups

- Automated: 1-35 days (1sec) -> s3 (free)
- Manual: DB snapshot

# 5. DynamoDB vs Elasticache

## 5.1. Dynamo

Amazon DynamoDB is a fully managed NoSQL database service provided by Amazon Web Services (AWS). It is designed for applications that require low-latency, high-performance access to large amounts of data. DynamoDB is particularly well-suited for use cases such as real-time analytics, gaming, IoT, mobile apps, and more.

## 5.2. Elasticache

Amazon ElastiCache is a fully managed in-memory data store and caching service provided by Amazon Web Services (AWS). It is designed to improve the performance of your web applications by enabling faster data retrieval from in-memory databases, which can significantly reduce the load on your primary database.

## 5.3. Difference

| **Feature**           | **Amazon DynamoDB**                                            | **Amazon ElastiCache**                                                  |
| --------------------- | -------------------------------------------------------------- | ----------------------------------------------------------------------- |
| **Purpose**           | Fully managed NoSQL database                                   | Fully managed in-memory data store and caching service                  |
| **Data Model**        | Key-value and document store                                   | Key-value store (supports Redis and Memcached)                          |
| **Data Storage**      | Persistent, stored on disk                                     | In-memory, typically non-persistent (Redis supports persistence)        |
| **Performance**       | Low latency, high throughput                                   | Extremely low latency, sub-millisecond response times                   |
| **Scalability**       | Automatically scales horizontally                              | Scales by adding nodes and increasing instance sizes                    |
| **Replication**       | Multi-region, automatic scaling, and global tables             | Supports replication (Redis) and automatic failover                     |
| **Data Durability**   | Durable with automatic backups and point-in-time recovery      | Volatile by default (Redis offers snapshot and AOF persistence options) |
| **Use Case**          | Applications needing reliable, scalable storage                | Applications needing fast, in-memory data access                        |
| **Common Use Cases**  | Real-time bidding, e-commerce, IoT, mobile apps                | Caching, session storage, real-time analytics, gaming leaderboards      |
| **Supported Engines** | Proprietary (AWS-built NoSQL service)                          | Redis, Memcached                                                        |
| **Capacity Modes**    | On-demand and provisioned capacity modes                       | Scales based on node addition and cluster configuration                 |
| **Security**          | Encryption at rest and in transit, fine-grained access control | Encryption, VPC integration, and IAM support                            |

# 6. Redshift 🟥

Amazon **Redshift** is a fully managed data warehouse service provided by AWS (Amazon Web Services) that enables businesses to analyze large datasets quickly and cost-effectively. Redshift is designed to handle complex queries and analytics on vast amounts of structured data, making it ideal for use cases such as business intelligence, data lakes, reporting, and data warehousing.

Here are key features and concepts of Amazon Redshift:

- Massively Parallel Processing (MPP): Redshift distributes data across multiple nodes in a cluster and processes queries in parallel, speeding up complex queries on large datasets.

- Columnar Storage: Instead of storing data in rows like traditional databases, Redshift stores data in columns, which reduces the amount of I/O required for queries, especially when only a few columns of data are needed.

- Scalability: Redshift allows you to easily scale up or down by adding or removing nodes to your cluster. You can start small and grow as your data and processing needs increase.

- Cost-Effective: It offers pay-as-you-go pricing and on-demand or reserved instance options, making it more affordable for large-scale data analytics compared to traditional on-premises data warehouses.

- Integration with AWS Ecosystem: Redshift integrates seamlessly with other AWS services, such as S3 (for data storage), Glue (for ETL jobs), Athena, and QuickSight (for data visualization), among others.

- Data Loading: You can load data into Redshift from multiple sources, such as Amazon S3, Amazon RDS, DynamoDB, or on-premises databases, using Redshift's COPY command, AWS Data Pipeline, or AWS Glue.

- Redshift Spectrum: This feature allows you to query data directly from S3 without having to load it into Redshift first, which makes it easier to query large data lakes.

- Security: Redshift offers encryption at rest and in transit, integrates with AWS IAM (Identity and Access Management), and supports Virtual Private Cloud (VPC) for network isolation.

Amazon Redshift is commonly used for data warehousing, business intelligence, analytics workloads, and complex reporting at scale.

# 7. Aurora DB ☁️

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
