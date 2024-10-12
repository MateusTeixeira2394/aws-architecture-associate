# 1. Aws Shield 🛡️

AWS Shield is a managed Distributed Denial of Service (DDoS) protection service that safeguards your applications hosted on AWS from DDoS attacks. There are two tiers of AWS Shield:

## 1.1. AWS Shield Standard

- **Automatic protection:** AWS Shield Standard is automatically included at no extra cost with AWS services like Amazon CloudFront, Elastic Load Balancing (ELB), and Route 53.
- **DDoS mitigation:** It protects against most common and smaller-scale network and transport layer DDoS attacks, such as SYN/ACK floods, reflection attacks, and slow HTTP attacks.
- **Monitoring:** It continuously monitors for DDoS attacks and automatically applies mitigations to protect your applications.

## 1.2. AWS Shield Advanced

- **Enhanced protection:** AWS Shield Advanced offers higher-level DDoS protection for more sophisticated and larger-scale attacks. It’s a paid service designed for mission-critical applications.
- **Layer 7 (application layer) protection:** It includes protection against more advanced attacks, such as those targeting the application layer.
- **Real-time attack visibility:** Shield Advanced gives you detailed metrics and real-time notifications about DDoS attacks through Amazon CloudWatch.
- **24/7 DDoS response team (DRT):** You get access to the AWS DDoS Response Team, which helps mitigate large-scale and sophisticated attacks.
- **Cost protection:** In case of a DDoS attack, AWS Shield Advanced offers cost protection for scaling-related charges incurred by the attack, such as surges in traffic to CloudFront.

## 1.3. Summary

AWS Shield helps ensure the availability and performance of your applications during DDoS attacks, making it a critical service for organizations that require high availability and resilience against cyberattacks.
