# 1. EBS 💽

**EBS (Elastic Block Store)** in AWS is a block storage service designed for use with Amazon EC2 instances. It provides persistent storage that can be attached to EC2 instances, allowing data to persist even after the instance is stopped or terminated. EBS volumes are highly available, durable, and can be used for a variety of workloads such as databases, file systems, and applications requiring block-level storage.

## 1.1. Key features

- **Persistent Storage**: Data remains intact even when EC2 instances are stopped.
- **Scalability**: You can dynamically increase the size, change the type, or adjust performance without downtime.
- **Snapshot Support**: EBS snapshots allow you to back up your volumes to Amazon S3 for data protection.
- **Types of EBS Volumes**: EBS offers various types of volumes optimized for different workloads, such as General - Purpose SSD (gp3), Provisioned IOPS SSD (io2), and Magnetic volumes.
- **Encryption**: EBS supports encryption for data at rest, in transit, and during snapshots.

EBS is often used for databases, file systems, and applications that require low-latency access to block storage.

![EBS diagram](../imgs/storage-ebs.jpg)

# 2. Kinds of EBS volumes 💿📀

| **Price** | **EBS Volume Type**               | **Use Case**                                                    | **Performance**                                  |
|-----------|------------------------------------|-----------------------------------------------------------------|--------------------------------------------------|
| 💵💵💵💵  | **I/O Operation Provisioned SSD IOPS (io2, io1)**| I/O-intensive apps: large databases, critical workloads         | io2: Up to 64,000 IOPS, higher durability         |
|           |                                    |                                                                 | io1: Up to 64,000 IOPS                            |
| 💵💵💵    | **General Purpose SSD (gp3, gp2)** | Most workloads: boot volumes, medium-sized databases, dev/test  | gp3: Up to 16,000 IOPS, 1,000 MB/s throughput     |
|           |                                    |                                                                 | gp2: Scales IOPS with size, up to 16,000 IOPS     |
| 💵💵      | **Throughput Optimized HDD Standard (st1)** | Big data, data warehouses, log processing, streaming workloads  | Optimized for throughput, up to 500 MB/s          |
| 💵        | **Cold HDD Standard Cold (sc1)**                 | Infrequently accessed data, backups, long-term storage          | Lower throughput but very cost-effective          |
| 🪙        | **Magnetic Volumes (Standard)** [Deprecated] | Previously used for lower performance demands, mostly replaced | Older technology, lower performance               |
