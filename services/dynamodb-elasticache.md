# 1. DynamoDB vs Elasticache

## 1.1. Dynamo

Amazon DynamoDB is a fully managed NoSQL database service provided by Amazon Web Services (AWS). It is designed for applications that require low-latency, high-performance access to large amounts of data. DynamoDB is particularly well-suited for use cases such as real-time analytics, gaming, IoT, mobile apps, and more.

## 1.2. Elasticache

Amazon ElastiCache is a fully managed in-memory data store and caching service provided by Amazon Web Services (AWS). It is designed to improve the performance of your web applications by enabling faster data retrieval from in-memory databases, which can significantly reduce the load on your primary database.

## 1.3. Difference

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
