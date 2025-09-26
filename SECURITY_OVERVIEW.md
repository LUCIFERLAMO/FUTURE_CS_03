# Security Overview: Secure File Sharing System

This document outlines the security architecture, encryption methods, and key handling procedures for the Secure File Sharing System project.

### Encryption Methods

The system is designed to protect files both at rest and in transit.

Encryption at Rest: All uploaded files are encrypted before being saved to the server's storage. The encryption algorithm used is **AES (Advanced Encryption Standard)** in **Cipher Block Chaining (CBC) mode** with a key size of 256 bits. This implementation is handled by the `PyCryptodome` library in Python. Each encrypted file is stored with its unique Initialization Vector (IV) prefixed to the ciphertext to ensure secure decryption.

Encryption in Transit: In a production environment, all communication between the user's browser and the web server would be secured using **HTTPS (TLS/SSL)**. This is typically configured on the production web server (e.g., Nginx or Apache) and ensures that file data is encrypted while it travels across the internet.

### Encryption Key Management

Secure handling of encryption keys is a critical component of this system.

* Current Implementation: For the purpose of this project, a **static, 256-bit (32-byte) AES key** is hardcoded directly into the `app.py` source code.

* Security Assessment: This approach is **not secure for a real-world application**. Hardcoding keys in source code is a major security risk, as anyone with access to the code can view the key and decrypt all files.

* Recommendations for Production: In a real system, the encryption key would be managed securely using one of the following methods:
    * Storing the key as an environment variable on the server.
    * Using a dedicated secret management service like AWS KMS, Google Cloud KMS, or HashiCorp Vault.
    * Loading the key from a protected configuration file with strict access controls.
