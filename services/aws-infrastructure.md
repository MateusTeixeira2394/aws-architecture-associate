# 1. Infrastructure 🏗️

The AWS has many data centers distributed to the whole world, according to the image below. To organize its infrastructure, the AWS divides it in **regions**, **available zone**, **local zone**, **wavelength** and **outputs**.

![AWS Infrastructure](../imgs/aws-infra.jpg)

## 1.1. Region

**Definition**: A region is a geographical area that contains multiple data centers. AWS divides the world into different regions to provide redundancy, fault tolerance, and low-latency access to its services.

**Characteristics**:
- **Geographical Separation**: Regions are physically isolated from each other.
- **Service Availability**: Each region has its own set of available services.
- **Data Residency**: Allows data to be stored in specific locations to comply with legal and regulatory requirements.

**Example**: `us-east-1` (North Virginia), `eu-west-1` (Ireland)

## 1.2. Available Zone (AZ)

**Definition**: An Availability Zone is a distinct location within a region that is engineered to be isolated from failures in other Availability Zones. Each AZ has its own power, cooling, and networking to ensure high availability.

**Characteristics**:
- **Redundancy**: Provides redundancy and failover options within a region.
- **High Availability**: Allows for deploying applications across multiple AZs to increase fault tolerance.
- **Low Latency**: Provides low-latency network connectivity to other AZs in the same region.

**Example**: `us-east-1a`, `us-east-1b`

## 1.3. Local Zone (LZ)

**Definition**: A Local Zone is an extension of an AWS region that is geographically closer to large population centers, providing low-latency access to AWS services.

**Characteristics**:
- **Proximity**: Located in major cities, offering reduced latency for applications that require proximity to end-users.
- **Partial Region Services**: Supports a subset of AWS services available in the main region.

**Example**: Local Zones in Los Angeles, Boston

## 1.4. Wavelength

**Definition**: AWS Wavelength extends AWS infrastructure to telecom networks, providing ultra-low latency and high-bandwidth access to applications running on AWS.

**Characteristics**:
- **Telecom Integration**: Deploys AWS services within telecom networks to deliver low-latency experiences.
- **Edge Computing**: Supports edge computing use cases, such as IoT and real-time data processing.

**Example**: Wavelength Zones in collaboration with carriers like Verizon and Vodafone

## 1.5. Outposts

**Definition**: AWS Outposts bring AWS hardware and services to on-premises locations, enabling a consistent hybrid cloud experience with native AWS services and APIs.

**Characteristics**:
- **On-Premises Deployment**: Provides AWS infrastructure on-premises to support workloads that require low latency or local data processing.
- **Consistency**: Offers the same AWS experience and APIs on-premises as in the AWS cloud.
- **Hybrid Cloud**: Integrates seamlessly with AWS cloud services for a unified hybrid cloud environment.

**Example**: AWS Outposts racks delivered to customer data centers



