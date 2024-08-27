# 1. Introduction 🚩

ELB stands for **Elastic Load Balancing** in AWS (Amazon Web Services). It is a service that automatically distributes incoming application traffic across multiple targets, such as Amazon EC2 instances, containers, IP addresses, and Lambda functions, in one or more Availability Zones. ELB helps ensure that your applications are highly available, fault-tolerant, and scalable.

# 2. Scaling up x Scaling out 📈

Scaling Up and Scaling Out are two different strategies for handling increased load on your applications, especially when using services like AWS Elastic Load Balancing (ELB). Here's the difference between the two:

## 2.1. Scaling up

- **Definition**: Scaling up, also known as **vertical scaling**, involves increasing the capacity of an existing resource, such as adding more CPU, memory, or disk space to a single server or instance.

- **Application in ELB**: While ELB itself is a distributed service and doesn’t "scale up" in the traditional sense, the instances behind the ELB can be scaled up. For example, you could upgrade your EC2 instances to more powerful ones (e.g., from a t3.medium to an m5.large instance) to handle more load on each individual instance.

- **Use Case**: Suitable for applications that are limited by the resources of a single instance. It's often easier to implement but may hit a limit based on the hardware or instance type.

## 2.2. Scaling out

- **Definition**: Scaling out, also known as horizontal scaling, involves adding more instances of a resource to distribute the load. Instead of making a single instance more powerful, you add more instances of the same type.

- **Application in ELB**: Scaling out is where ELB truly shines. You can add more EC2 instances behind the load balancer, and ELB will automatically distribute the incoming traffic across all available instances. This approach increases the overall capacity and redundancy of your application.

- **Use Case**: Ideal for applications that can run on multiple instances in parallel. It provides better fault tolerance and can scale indefinitely (or up to the limits of the AWS service).

# 3. Auto Scaling

**Auto Scaling** in AWS is a service that automatically adjusts the number of compute resources, such as Amazon EC2 instances, based on the current demand for your application. It helps maintain application availability and allows you to scale your resources up or down automatically according to defined conditions.

## 3.1. Key Features of AWS Auto Scaling

1. **Dynamic Scaling**
   - Automatically adjusts the number of running instances in response to changing demand. For example, you can set policies to add more instances during high traffic periods and remove instances when demand decreases.

2. **Scheduled Scaling**
   - Allows you to scale your resources based on a schedule. For instance, you can automatically scale out your instances at a specific time of day when you expect high traffic.

3. **Predictive Scaling**
   - Uses machine learning models to predict traffic patterns and automatically adjust your resources in advance of expected demand changes.

4. **Health Checks and Replacement**
   - Auto Scaling performs health checks on the instances in your Auto Scaling group. If it finds an instance that is unhealthy, it can terminate the instance and launch a new one to replace it.

5. **Cost Efficiency**
   - Helps optimize costs by scaling down resources when they are not needed, thus reducing the number of instances running during low-traffic periods.

6. **Integration with Elastic Load Balancing (ELB)**
   - Auto Scaling works seamlessly with ELB to distribute traffic across your instances. When new instances are launched, they are automatically added to the ELB, and when instances are terminated, they are removed from the load balancer.

## 3.2. How Auto Scaling Works

1. **Auto Scaling Groups**
   - The core concept of Auto Scaling is the Auto Scaling Group, which is a collection of EC2 instances managed as a group. You define the minimum, maximum, and desired number of instances in the group.

2. **Scaling Policies**
   - You can define policies that dictate when and how Auto Scaling should adjust the number of instances. These policies can be based on metrics like CPU utilization, request count, or even custom metrics you define.

3. **Launch Configuration/Launch Template**
   - Specifies the configuration information for instances in the Auto Scaling group, including instance type, Amazon Machine Image (AMI), key pairs, security groups, and block device mapping.

## 3.3. Use Cases

- **Handling Variable Traffic:** Automatically scale your web or application servers up during peak hours and down during off-peak hours.
- **Maintaining High Availability:** Ensure that your application remains available by automatically replacing failed instances.
- **Optimizing Costs:** Run only the instances you need, scaling down when demand is low to save on costs.

AWS Auto Scaling simplifies the management of compute resources, ensuring that your application remains responsive and cost-efficient by automatically adjusting the capacity to match the demand.

![Auto Scaling image](./imgs/elb-auto-scaling.jpg)

# 4. Load Balancers

to do


