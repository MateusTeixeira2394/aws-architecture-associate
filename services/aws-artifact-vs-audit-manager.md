# Difference Between AWS Audit Manager and AWS Artifact

## AWS Audit Manager:

**AWS Audit Manager** helps automate the auditing process for your AWS resources, making it easier to collect and manage audit evidence for compliance with various regulatory frameworks. Its key features include automated evidence collection, continuous monitoring, and pre-built/custom compliance frameworks. Audit Manager continuously tracks AWS resource configurations and activities, generating reports and assessments that auditors can use to evaluate compliance.

### Key Features:

- Automated evidence collection from AWS services (e.g., CloudTrail, Config).
- Pre-built compliance frameworks (e.g., SOC 2, ISO 27001, HIPAA).
- Customizable frameworks to meet specific compliance requirements.
- Continuous monitoring of AWS resources.
- Assessment reports to support audits.

### Use Case:

- Best suited for **ongoing compliance management**, where you need to continuously collect and evaluate evidence of your AWS environment's compliance over time.

---

## AWS Artifact:

**AWS Artifact** is a self-service portal that provides access to AWS’s compliance reports and agreements. It’s primarily a repository for pre-existing documents that demonstrate AWS’s compliance with industry standards and regulations. These reports can be downloaded and shared with auditors or stakeholders to show how AWS services comply with security, privacy, and regulatory requirements.

### Key Features:

- Provides access to AWS compliance reports (SOC reports, ISO certifications, PCI DSS reports, etc.).
- Allows you to view and accept agreements like HIPAA Business Associate Addendum (BAA) and GDPR Data Processing Addendum (DPA).
- On-demand access to compliance documents through the AWS Management Console.

### Use Case:

- Best suited for **auditors or compliance teams** needing AWS's official reports and certifications to demonstrate compliance, but does not automate the auditing process for the customer's own AWS resources.

---

## Main Differences:

| Feature                   | AWS Audit Manager                                           | AWS Artifact                                                  |
| ------------------------- | ----------------------------------------------------------- | ------------------------------------------------------------- |
| **Purpose**               | Automates auditing of AWS resources and evidence collection | Provides access to AWS compliance reports and agreements      |
| **Compliance Management** | Continuous compliance monitoring and assessment             | Static compliance documentation repository                    |
| **Customization**         | Supports pre-built and custom compliance frameworks         | No customization – provides standard AWS compliance documents |
| **Evidence Collection**   | Automatically collects evidence from AWS resources          | Does not collect evidence; provides AWS's compliance reports  |
| **Use Case**              | Ongoing internal auditing and compliance management         | Proof of AWS’s compliance with industry standards for audits  |

## Summary:

- **AWS Audit Manager** is designed for organizations looking to continuously monitor and audit their AWS resources for compliance.
- **AWS Artifact** is more of a document repository, offering access to official AWS compliance reports and agreements for organizations to share with auditors or stakeholders.
