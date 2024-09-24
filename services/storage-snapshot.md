# 1. Snapshot 📸

A snapshot in AWS EBS (Elastic Block Store) is a point-in-time backup of an EBS volume. **It captures the state of the volume at the time the snapshot is taken**, allowing you to create backups, restore data, and create new EBS volumes from the snapshot. Here’s a breakdown of how snapshots work and their key features:

## 1.1. Key features:

- Point-in-Time Backup:
    - A snapshot records the state of an EBS volume at a specific moment. It includes all the data present on the volume at that time.

- Incremental Backup:
    - After the first snapshot, which is a full backup, subsequent snapshots are incremental. This means that only the data that has changed since the last snapshot is saved, reducing storage costs and improving efficiency.

- Stored in Amazon S3:
    - Snapshots are stored in Amazon S3 (though not directly visible in S3) and are designed for durability and availability. However, they don’t count against your S3 storage limits since AWS manages the storage separately.

- Restoration:
    - You can restore a volume from any snapshot to create a new EBS volume. The new volume will be in the exact state as the volume was when the snapshot was taken.
Snapshots can be restored to volumes of different sizes or types, providing flexibility in volume management.

- Cross-Region and Cross-Account Copying:
    - You can copy snapshots between AWS regions, enabling disaster recovery setups, or share them with other AWS accounts.

- Automatic Snapshots:
    - EBS allows you to automate the snapshot process using AWS tools like Data Lifecycle Manager (DLM), where you can schedule regular snapshots of your volumes for backup and disaster recovery purposes.

- Encryption:
    - If your EBS volume is encrypted, the snapshots will also be encrypted, and any new volumes created from those snapshots will inherit the encryption settings.

## 1.2. Common use cases:

- **Backup & Recovery**: Snapshots provide a reliable backup solution to restore your data in case of accidental data loss, corruption, or system failure.
- **Data Migration**: Snapshots can be used to transfer data across regions or between different AWS accounts.
- **Volume Replication**: Snapshots can be used to create new volumes in different regions or availability zones for replication, scaling, or testing purposes.

## 1.3. Snapshot process flow:

1. Take a snapshot of an EBS volume.
2. The snapshot is stored in S3 as an incremental backup.
3. When needed, restore a snapshot to create a new EBS volume or use it as part of disaster recovery.

## 1.4. Moving the EBS volume to another AZ

EBS (Elastic Block Store) volumes can only be attached to EC2 instances that are in the **same Availability Zone (AZ)**, however, there are two ways to migrate a EBS volume to another AZ:

![Migrating EBS volume to another AZ diagram](../imgs/storage-moving-ebs.jpg)
