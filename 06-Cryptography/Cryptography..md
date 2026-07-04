# Cryptography

---

## **What is Cryptography?**

**The science of SECURE COMMUNICATION** - protecting information from unauthorized access.

---

## **Core Concepts:**

### **1. Encryption vs Decryption**

- **Encryption:** Scramble data → **plaintext** → **ciphertext**
- **Decryption:** Unscramble data → **ciphertext** → **plaintext**

### **2. Key Types:**

### **Symmetric Encryption (Private Key)**

- **One key** for both encryption AND decryption
- **Like:** Same key locks and unlocks a door
- **Examples:** AES, DES, 3DES
- **Fast** but key distribution is hard

### **Asymmetric Encryption (Public Key)**

- **Two keys:** Public (encrypt) + Private (decrypt)
- **Like:** Open padlock (public) + Unique key (private)
- **Examples:** RSA, ECC, Diffie-Hellman
- **Slow** but solves key distribution

### **3. Hashing (One-way)**

- **Convert data** → fixed-size string (hash)
- **Cannot be reversed**
- **Examples:** SHA-256, MD5
- **Used for:** Data integrity, passwords

### **4. Digital Signatures**

- **Prove identity** and **data integrity**
- **How:** Hash data + encrypt with private key
- **Verify with** sender's public key
