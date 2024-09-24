# 1. AMI 🖼️

An AWS **AMI (Amazon Machine Image)** is a template that contains the necessary information to launch a virtual server (EC2 instance) in the Amazon Web Services (AWS) cloud. It serves as a blueprint for creating instances, allowing you to quickly deploy pre-configured environments. Here’s what it includes and how it works:

## 1.1. Key features

- Operating System (OS):

    - The AMI includes the operating system that will run on your EC2 instance. This can be Linux (e.g., Ubuntu, Amazon Linux) or Windows Server, among others.

- Application Server and Software:
    - AMIs can come pre-installed with specific software, application servers, or configurations, such as a web server (Apache, Nginx), databases, or even entire application stacks (e.g., LAMP stack).

- EBS Snapshots:
    - AMIs include one or more EBS snapshots of the root volume (and any attached volumes), which store the contents of the system's disk at the time the AMI was created.

- Permissions:
    - AMIs can be made private (accessible only to your AWS account), shared with specific AWS accounts, or made public for other users to use.

- Launch Permissions:
    - These permissions control who can use the AMI to launch EC2 instances. Public AMIs can be used by anyone, while private AMIs are restricted to specific accounts.

- Instance Types:
    - You can specify the instance type (such as t2.micro or m5.large) when launching an instance from an AMI. The instance type determines the hardware resources like CPU, memory, and storage.

## 1.2. Types of AMIs

- Public AMIs:
    - Provided by AWS or third-party vendors, these AMIs are available for anyone to use. Examples include standard OS images like Amazon Linux or Ubuntu.

- Private AMIs:
    - Created by you or shared with you, these are custom images only accessible to your AWS account or specific accounts you share it with.

- Marketplace AMIs:
    - Available through the AWS Marketplace, these are pre-configured AMIs built by vendors and developers, often tailored for specific applications, services, or software needs.

## 1.3. Common use cases

- **Quick Deployment**: AMIs allow you to rapidly deploy pre-configured environments with a chosen OS, software, and settings.
- **Backup & Disaster Recovery**: You can create custom AMIs as backups of your current server setup, enabling easy recovery or scaling if needed.
- **Custom Environments**: AMIs can be customized to include specific applications or software configurations that meet your business requirements.

## 1.4. AMI Lifecycle

1. Create an AMI: You can create a custom AMI from an existing EC2 instance. This AMI will contain the OS, applications, and data from the instance at the time the AMI is created.
2. Launch an Instance: Use the AMI to launch new EC2 instances. These instances will start with the OS, software, and data from the AMI.
3. Share or Distribute: You can share your custom AMIs with other AWS accounts or the public if desired.
