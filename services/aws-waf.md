# 1. AWS WAF (Web Application Firewall) 🔥🧱

**AWS WAF** is a cloud-based web application firewall service that helps protect your web applications from common web exploits and attacks that can affect availability, compromise security, or consume excessive resources. AWS WAF allows you to monitor and control incoming and outgoing HTTP(S) requests to your applications by defining customizable security rules.

## 1.1. Key Features of AWS WAF:

1. **Protection Against Common Attacks**:

   - AWS WAF helps protect your web applications from:
     - **SQL Injection**: Prevents database manipulation attacks.
     - **Cross-Site Scripting (XSS)**: Protects against malicious script injections.
     - **Other Threats**: Protects from vulnerabilities like bad bots, DDoS attacks, and more.

2. **Customizable Rules**:

   - Define rules to filter traffic based on:
     - **IP addresses**.
     - **Geographic location**.
     - **Request patterns** (URI, headers, HTTP methods, query strings).
     - **Rate limiting** to throttle excessive requests.

3. **Preconfigured Managed Rules**:

   - Use managed rule groups, pre-configured by AWS or AWS Marketplace vendors, for common security threats like the **OWASP Top 10 vulnerabilities**.

4. **Real-Time Monitoring and Visibility**:

   - AWS WAF integrates with **Amazon CloudWatch** for real-time monitoring, logging, and metric tracking, allowing you to monitor how rules are being applied to traffic.

5. **Integration with AWS Services**:
   - AWS WAF works with:
     - **Amazon CloudFront**: Protects web applications served via AWS's global CDN.
     - **Application Load Balancer (ALB)**: Protects apps using ALBs.
     - **Amazon API Gateway**: Secures APIs from web-based attacks.
     - **AWS App Runner**: Secures containerized applications and microservices.

## 1.2. Use Cases for AWS WAF:

- **Web Application Protection**: Block web exploits such as SQL injections, XSS, and more.
- **Bot Mitigation**: Detect and block malicious bot traffic.
- **Geographical Blocking**: Allow or block traffic based on the originating country.
- **API Protection**: Protect APIs from unauthorized access and attacks.
- **Rate Limiting**: Throttle excessive traffic to prevent denial-of-service attacks.

## 1.3. How AWS WAF Works:

1. **Define Rules**: You create rules to specify conditions for what traffic to allow or block.
2. **Apply Web ACLs**: Apply rules to a **Web ACL** (Access Control List) that is associated with resources like CloudFront, ALB, or API Gateway.
3. **Monitor Traffic**: AWS WAF inspects requests and applies the rules in real-time.
4. **Logging and Alerts**: You can log rule matches and configure alerts with **CloudWatch**.

## 1.4. Benefits of AWS WAF:

- **Improved Security**: Protect web applications from common threats without impacting performance.
- **Flexible and Scalable**: Define custom rules and automatically scale as traffic grows.
- **Cost-Effective**: Pay only for what you use with AWS’s **pay-as-you-go** pricing model.

In summary, AWS WAF is a highly customizable, scalable, and secure web application firewall designed to protect web applications from common web-based threats such as SQL injection, XSS, and DDoS attacks.

## 1.5. Aws WAF Vs GuardDuty

[Aws WAF Vs Amazon GuardDuty](./guardduty-vs-waf.md)
