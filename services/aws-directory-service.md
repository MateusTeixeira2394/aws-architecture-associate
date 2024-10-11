# 1. AWS Directory Service 🗂️

Active Directory (AD) is a directory service developed by Microsoft that provides a centralized platform for managing and organizing users, computers, devices, and other resources in a network. It allows administrators to control permissions, apply policies, and authenticate users within an organization.

## 1.1. Key Components of Active Directory:

- **Domain:** A logical group of objects (users, computers, devices) that share the same AD database and security policies. Each domain has a unique namespace.
- **Domain Controller (DC):** A server that hosts the AD database and handles user authentication and authorization.
- **Organizational Units (OUs):** Containers within a domain used to group users, groups, or computers. OUs simplify administration and allow policies to be applied at different levels.
- **Forest:** The top-level structure of Active Directory that contains one or more domains. A forest represents the security boundary.
- **Tree:** A collection of one or more domains that share a contiguous namespace within a forest.
- **Groups:** Objects that can contain multiple users or other groups, allowing for easier management of permissions and resources.
- **Global Catalog:** A distributed data repository that stores a partial replica of every object in the forest. It helps in speeding up search queries and enabling cross-domain resource access.

## 1.2. Core Functions of Active Directory:

- **Authentication:** AD authenticates users who attempt to log in to the network, ensuring that they are who they claim to be.
- **Authorization:** Once authenticated, AD grants or restricts access to network resources based on the user’s permissions and group memberships.
- **Centralized Management:** Admins can manage all network resources (users, devices, applications) from a central point using AD.
- **Group Policy:** AD allows administrators to apply security policies, configurations, and software deployment across many computers at once using Group Policy Objects (GPOs).
- **Single Sign-On (SSO):** With AD, users can log in once and gain access to multiple resources and applications without re-authenticating.

## 1.3. Use Cases:

- **Enterprise Networks:** AD is widely used in corporate environments to manage employees’ access to computers, shared resources, and applications.
- **User Authentication:** AD enables secure user login across Windows and non-Windows systems (through protocols like LDAP and Kerberos).
- **Access Control:** Administrators can define fine-grained access controls to determine who can view, modify, or access resources on the network.

Overall, Active Directory is a foundational technology for identity and access management (IAM) in Windows-based IT environments.
