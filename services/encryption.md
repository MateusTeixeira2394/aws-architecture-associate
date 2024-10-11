# 1. Encryption 🔒🔑

**Encryption** is the process of converting data into a coded format to prevent unauthorized access. It ensures that sensitive information is protected from eavesdropping and unauthorized use by transforming readable data (plaintext) into an unreadable format (ciphertext) using a specific algorithm and a key.

## 1.1. Key features

- **Plaintext**: The original, readable data that is to be encrypted.
- **Ciphertext**: The encrypted data that is unreadable without decryption.
- **Encryption Algorithm**: A mathematical procedure used to transform plaintext into ciphertext. Common algorithms include **AES** (Advanced Encryption Standard), **RSA** (Rivest-Shamir-Adleman), and **DES** (Data Encryption Standard).
- **Key**: A piece of information (a string of bits) used by the encryption algorithm to perform the encryption and decryption processes. The security of the encryption largely depends on the secrecy of the key.
- **Decryption**: The process of converting ciphertext back into plaintext using a decryption key or algorithm.

## 1.2. Types of encryption

- **Symmetric Encryption**:

  - The same key is used for both encryption and decryption. This method is faster and more efficient for encrypting large amounts of data. Example algorithms include AES and DES.

- **Asymmetric Encryption**:

  - Uses a pair of keys: a public key for encryption and a private key for decryption. This method is often used for secure communications and digital signatures. An example of an asymmetric algorithm is RSA.

- **In Transit**:
  - Data that is being transferred between two locations, such as over the internet or between servers, is considered "in transit." This includes data sent over networks, such as emails, web traffic, and file transfers.
  - This typically falls under transport encryption or data-in-transit encryption. It involves encrypting data as it moves from one location to another to protect it from interception and unauthorized access during transmission.
  - **Common Protocols**:
    - TLS (Transport Layer Security): Used for securing communications over a computer network (e.g., HTTPS).
    - SSH (Secure Shell): Used for secure remote access and file transfers.
    - VPN (Virtual Private Network): Creates secure connections over the internet.
- **At rest**:
  - Data that is stored on a device or server and not actively being transferred is considered "at rest." This includes data saved in databases, files on hard drives, and backups.
  - This falls under data-at-rest encryption. It involves encrypting stored data to protect it from unauthorized access, theft, or breaches while it is not being transferred.
  - **Common methods**:
    - **Full Disk Encryption**: Encrypts the entire storage device (e.g., BitLocker for Windows, FileVault for macOS).
    - **Database Encryption**: Specific encryption mechanisms applied to database files or individual records.
    - **File Encryption**: Encrypting individual files to protect sensitive data.

![Encryption diagram](../imgs/security-encryption.jpg)
