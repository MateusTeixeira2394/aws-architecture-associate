# 1. Introduction 🚩

DNS, or **Domain Name System**, is a fundamental part of the internet's infrastructure. It translates human-friendly domain names into IP addresses, which computers use to identify each other on the network. Here’s a breakdown of how DNS works and its key components:

## 1.2. Purpose of DNS

- **Domain Name to IP Address Translation:**
  - Humans use domain names (like `www.example.com`) to access websites and services because they are easier to remember than numeric IP addresses (like `192.0.2.1`).
  - DNS translates these domain names into IP addresses so that computers can communicate with each other over the internet.

## 1.3. How DNS Works

1. **User Request:**

   - When you enter a URL in your browser, it needs to find the corresponding IP address to connect to the server.

2. **DNS Query:**

   - Your computer sends a DNS query to a DNS resolver (often provided by your ISP or a public DNS service).

3. **DNS Resolver:**

   - The resolver is responsible for querying DNS servers to find the IP address associated with the domain name.

4. **Recursive Lookup:**

   - The resolver starts by asking root DNS servers for information about the domain. Root servers direct the resolver to top-level domain (TLD) servers (.com, .org, etc.).

5. **TLD Servers:**

   - TLD servers direct the resolver to authoritative DNS servers for the domain.

6. **Authoritative DNS Servers:**

   - These servers hold the actual DNS records for the domain. They provide the resolver with the IP address.

7. **Response:**

   - The resolver sends the IP address back to your computer, which then uses it to connect to the web server hosting the website.

8. **Caching:**
   - To speed up future requests, the IP address and domain name are cached by the resolver and your computer for a period of time (determined by the Time-To-Live or TTL value in the DNS records).

![Diagram of how the dns works](./imgs/dns-how-it-works.jpg)

## 1.3. Key Components of DNS

1. **Domain Names:**

   - Structured hierarchically. For example, in `www.example.com`, `com` is the top-level domain (TLD), `example` is the second-level domain, and `www` is a subdomain.

2. **DNS Records:**

   - **A Record:** Maps a domain name to an IPv4 address.
   - **AAAA Record:** Maps a domain name to an IPv6 address.
   - **CNAME Record:** Maps a domain name to another domain name (canonical name).
   - **MX Record:** Specifies mail exchange servers for the domain.
   - **NS Record:** Specifies authoritative DNS servers for the domain.
   - **TXT Record:** Allows the domain to hold arbitrary text, often used for verification and security purposes.

3. **DNS Servers:**
   - **Root DNS Servers:** The top-level servers that direct queries to TLD servers.
   - **TLD DNS Servers:** Handle the TLDs and direct queries to the authoritative servers.
   - **Authoritative DNS Servers:** Store DNS records for specific domains and provide the final answer for DNS queries.

## 1.4. DNS Caching

- **Local Cache:**

  - Your computer and DNS resolver cache DNS records to reduce lookup times and avoid excessive querying.

- **DNS TTL (Time-To-Live):**
  - Specifies how long a DNS record is cached before it needs to be refreshed.

## 1.4. Summary

DNS is crucial for translating domain names into IP addresses, allowing users to access websites and services using human-readable names. It operates through a hierarchy of servers and records, with caching to improve efficiency and performance.

# 2. Route53 🛣️

**Amazon Route 53** is a scalable and highly available DNS web service provided by AWS. It helps in translating domain names (like www.example.com) into IP addresses, which are needed for computers to connect to each other over the internet. Route 53 is also designed to be flexible and secure, offering more than just basic DNS resolution.

## 2.1. Key Features

- DNS Management:

  - Route 53 provides DNS resolution by mapping domain names to IP addresses for AWS services (like EC2, S3) as well as external resources.
  - Supports common DNS record types like A, AAAA, CNAME, MX, TXT, NS, etc.

- Domain Registration:

  - You can purchase and manage domain names directly through Route 53. It acts as a domain registrar, allowing you to register and transfer domains.

- Traffic Routing:

  - Latency-based Routing: Route 53 directs users to the AWS region or endpoint that provides the lowest latency.
  - Geo-Location and Geo-Proximity Routing: Routes traffic based on the geographic location of users or resources.
  - Weighted Routing: Distributes traffic across multiple endpoints based on specified weights (for load balancing or testing).
  - Failover Routing: Detects the health of resources and redirects traffic to healthy endpoints during failures.

- Health Checks and Monitoring:

  - Route 53 can perform health checks on your web servers or other endpoints. If it detects that a resource is unavailable, it will automatically route traffic to healthy resources.

- DNS Failover:

  - In case of server or application failures, Route 53 can switch traffic to backup resources, improving availability and reliability.

- Integration with AWS Services:

  - Deep integration with other AWS services, like EC2, Elastic Load Balancing (ELB), S3, CloudFront, and others, making it easier to set up and manage routing for applications hosted on AWS.

- Security:

  - Route 53 supports DNSSEC (Domain Name System Security Extensions) to protect against DNS spoofing and man-in-the-middle attacks.
  - It also integrates with AWS Identity and Access Management (IAM) for access control and permissions management.

## 2.2. Pricing

While traditional DNS providers charge mostly a **fixed, upfront annual fee, regardless of traffic**, the AWS Route 53 operates on a **pay-as-you-go** model where you are **charged based on usage**, such as the number of DNS queries and hosted zones. This can be more cost-effective for low-traffic domains, but for high-traffic domains, the costs may increase depending on the level of usage.

## 2.3. Summary

Amazon Route 53 is not a DNS service with domain registration, it also handles traffic routing, health checks, and integration with AWS services, making it essential for managing scalable and reliable web applications.

# 3. Hosted Zones 📦📍

In AWS Route 53, a Hosted Zone is a container that holds information about how to route traffic for a specific domain (like example.com) and its subdomains. It functions as the DNS (Domain Name System) zone for the domain, which translates human-readable domain names into IP addresses that computers use to connect to each other.

## 3.1. Public Hosted Zone

This is used to manage DNS records for a domain that is accessible over the internet. When you register a domain or transfer it to Route 53, a public hosted zone is automatically created. This hosted zone allows you to create DNS records like **A (IPv4 address)**, **CNAME (Canonical Name)**, **MX (Mail Exchange)**, and others to direct traffic to your website or services.

## 3.2. Private Hosted Zone

This is used within an Amazon VPC (Virtual Private Cloud) to manage DNS records for internal routing of domain names that are **only accessible within the VPC**. It helps in managing domain names for resources inside your VPC, such as EC2 instances, without exposing them to the public internet.

# 4. Route 53 Polices 📜

## 4.1. Simple Routing Policy

- **Usage**: This is the default routing policy. It allows you to configure DNS records to return a single resource, such as an IP address or endpoint.
- **Scenario**: If you want to route traffic to a single resource, like a web server or a static website hosted on S3.

## 4.2. Weighted routing policy

- **Usage**: Routes traffic to multiple resources in proportions that you specify.
- **Scenario**: If you want to test new application versions by sending a small percentage of traffic to the new version while keeping most traffic on the old version.

## 4.3. Geolocation routing policy

- **Usage**: Routes traffic based on the geographic location of the user making the DNS query.
- **Scenario**: If you want users in Europe to be routed to European servers, and users in the US to North American servers.

## 4.4. Geoproximity routing policy

- **Usage**: Routes traffic based on the geographic location of your resources and allows you to adjust bias to route more or less traffic to specific resources. Obs: It is the unique routing policy that is created through Traffic Flow.
- **Scenario**: If you have resources in multiple regions and want to control the traffic distribution to them by location.

## 4.5. Latency routing policy

- **Usage**: Routes traffic to the resource that provides the lowest latency to the user based on network performance. It's not obligation to be the nearest server. Sometimes, there is a farer one, but with better latency.
- **Scenario**: If you have resources in different AWS regions and want to route traffic to the one with the best performance for the user.

## 4.6. Failover Routing

- **Usage**: This policy routes traffic to a primary resource, such as a web server, and directs traffic to a secondary resource (or failover instance) only if the primary fails. The route 53 knows that through health check.
- **Scenario**: Useful for implementing disaster recovery solutions.

## 4.7. Multivalue Answer Routing

- **Usage**: Provides multiple IP addresses (up to 8) in response to a DNS query and allows health checks on each.
- **Scenario**: Ideal for distributing traffic across multiple resources and providing DNS failover if any resource becomes unhealthy.

![Route 53 routing polices](./imgs/dns-route-53-routing-polices.jpg)

# 5. Traffic Policy 👮🏽‍♂️

A Traffic Policy in AWS Route 53 is a powerful feature that allows you to define complex routing configurations for your DNS traffic using a combination of routing rules. It enables more advanced traffic management and routing strategies by allowing you to create a traffic flow policy that incorporates multiple routing policies in a single configuration.

## 5.1. Key features

-**Visual Editor**: You can design traffic policies using a visual editor, allowing you to easily combine different routing policies, such as weighted, latency-based, geolocation, and more, into a single flow.

- **Reusability**: Once you create a traffic policy, it can be reused across multiple domains (hosted zones), allowing you to apply the same routing rules to different DNS names.

- **Versioning**: Traffic policies support versioning, which means you can update and change a traffic policy over time, keeping track of changes without affecting live traffic until you choose to.

- **Traffic Policy Instances**: Once a traffic policy is created, you apply it to DNS names by creating traffic policy instances. These instances define how a specific policy will be applied to a DNS name in a hosted zone.

# 6. Route 53 Resolver 🕵🏽

**Route 53 Resolver** is a DNS service within AWS Route 53 that helps manage DNS queries between on-premises networks and AWS VPCs (Virtual Private Clouds). It acts as a DNS resolver that handles both inbound and outbound DNS queries, facilitating seamless communication between AWS resources and external networks.

## 6.1. Key features

- Inbound Query Forwarding:
   - Allows on-premises networks to resolve DNS names hosted within AWS (e.g., EC2 instances in private VPCs) by forwarding DNS queries to Route 53 Resolver.
   - Use case: If you have resources in AWS VPCs that need to be accessible by name from your on-premises data center or other external networks.

- Outbound Query Forwarding:
   - Enables AWS resources (e.g., EC2 instances) in a VPC to resolve DNS names from external networks (e.g., on-premises domains or other DNS systems).
   - Use case: If your EC2 instances or other AWS services need to access on-premises systems or external services by their DNS name.

- DNS Resolution Between VPCs:
   - Facilitates DNS resolution between multiple VPCs within the same or different AWS regions using VPC peering or AWS Transit Gateway.

- Conditional Forwarding:
   - Route 53 Resolver supports conditional forwarding rules that direct specific DNS queries (based on domain names) to different DNS servers. This allows for complex DNS resolution across hybrid cloud environments.

- Integration with AWS VPC:
   - Route 53 Resolver is automatically integrated with Amazon VPC, so DNS queries from EC2 instances are automatically resolved to appropriate resources, like other VPC resources, without requiring external DNS services.

## 6.2. Benefits:
- Hybrid Cloud DNS Management: Route 53 Resolver is key for hybrid environments, where resources span across both on-premises data centers and AWS cloud environments.
- Scalability and Availability: Like other AWS services, Route 53 Resolver is scalable and highly available, ensuring consistent DNS query performance across networks.
- Security: DNS queries can be controlled and monitored with AWS services like VPC flow logs, providing visibility into DNS traffic patterns.

![Route 53 resolver diagram](./imgs/dns-route-53-resolver.jpg)

# 7. Cloudfront ☁️🌎

Amazon **CloudFront** is a **Content Delivery Network (CDN)** service provided by AWS that securely delivers content (such as websites, APIs, videos, or software) to users globally with low latency and high transfer speeds. It acts as a distribution network of globally located servers (called edge locations) that cache and serve content to users from the closest server, improving performance and reliability.

![Cloudfront image](./imgs/dns-cloudfront.jpg)

## 7.1. Key features:
- Global Edge Locations:
   - CloudFront uses a network of edge locations distributed around the world. When a user requests content, CloudFront serves it from the edge location closest to them, reducing latency.

- Content Caching:
   - CloudFront caches your content at edge locations, speeding up the delivery of frequently requested content like images, videos, and static files. The content is stored temporarily at these edge locations and is refreshed periodically.

 - Support for Dynamic and Static Content:
   - CloudFront can deliver both static content (e.g., images, CSS, JavaScript files) and dynamic content (e.g., API responses, personalized content, or database-driven content). For dynamic content, CloudFront works with features like Lambda@Edge for real-time customization.

- Security:
   - CloudFront integrates with AWS services like AWS Shield for DDoS protection and AWS WAF (Web Application Firewall) for application-layer security. It also supports SSL/TLS encryption for secure content delivery and signed URLs to restrict access to certain content.

- Custom Origins:
   - CloudFront can pull content from multiple sources, including Amazon S3 buckets, Elastic Load Balancers, or even non-AWS web servers, referred to as custom origins.

- Compression and Optimization:
   - CloudFront automatically compresses files like HTML, CSS, and JavaScript to reduce the size of the data being transferred, resulting in faster load times for end users.

- Content Delivery with Lambda@Edge:
   - With Lambda@Edge, you can run code closer to users to customize and personalize the content CloudFront delivers. This allows you to modify requests or responses in real time without having to maintain servers.

- Origin Failover:
   - CloudFront provides origin failover, allowing you to specify backup origins. If CloudFront cannot retrieve content from the primary origin, it automatically fetches it from the secondary origin, improving availability.

- Real-Time Monitoring:
   - CloudFront integrates with Amazon CloudWatch, allowing you to monitor CDN performance, usage, and errors in real time. It also provides detailed analytics about request activity, cache hits/misses, and geographic distribution.

   ![Cloudfront diagram](./imgs/dns-cloudfront-diagram.jpg)

   ## 7.2. OAI

   OIA in AWS CloudFront stands for **Origin Access Identity**. It is a feature used to restrict access to an Amazon S3 bucket that is being used as the origin for a CloudFront distribution. The goal of OIA is to ensure that your S3 content is only accessible through CloudFront and not directly from the S3 bucket's public URL, thus enhancing security and control over content delivery.
   When it's enabled, a **policy is created** to restrict the origin accesses directly.

   ## 7.3. Lambda Edge

   **Lambda Edge** is an AWS feature that allows you to run serverless code closer to your users by executing AWS Lambda functions at CloudFront edge locations, before or after each request and before or after each response, like the image below. This enables you to customize and modify the content delivered by CloudFront in real time, without managing servers. Lambda Edge helps improve performance and allows you to apply logic at the edge, resulting in faster responses and highly customizable content.

   ![Lambda Edge diagram](./imgs/dns-lambda-edge.jpg)