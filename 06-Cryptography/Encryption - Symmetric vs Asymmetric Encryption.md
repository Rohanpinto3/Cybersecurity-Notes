# Encryption - **Symmetric vs Asymmetric Encryption**

---

Encryption = Scrambling data so only authorized people can read it..

Simple Analogy:
Plaintext = Your secret message: "Attack at dawn"

Encryption = Put message in locked box 🔒

Ciphertext = Scrambled gibberish: "X7#gM!pQ2$kL@9"

Decryption = Unlock box with key

**Symmetric vs Asymmetric Encryption** 🔐

---

## **Symmetric Encryption (Private Key)**

**"One Key Fits All"** 🗝️

### **How it works:**

- **Same key** for both **encryption AND decryption**
- **Like:** Your house key - same key locks and unlocks

### **Examples:**

- **AES** (Advanced Encryption Standard) - Most common today
- **DES** (Data Encryption Standard) - Old, broken
- **3DES** - Triple DES, more secure

### **Pros:**

- ✅ **Very FAST** - Good for large amounts of data
- ✅ **Simple** - Easy to implement

### **Cons:**

- ❌ **Key distribution problem** - How to securely share the key?
- ❌ **Not scalable** - Need different keys for different people

**Use case:** Encrypting your hard drive, database encryption

---

## **Asymmetric Encryption (Public Key)**

**"Lock and Key System"** 🔓🗝️

### **How it works:**

- **Two keys:**
    - **Public Key** = **LOCK** (anyone can encrypt)
    - **Private Key** = **KEY** (only you can decrypt)
- **Like:** A padlock - anyone can lock it, but only key holder can open

### **Examples:**

- **RSA** - Most common
- **ECC** (Elliptic Curve) - Newer, more efficient
- **Diffie-Hellman** - Key exchange

### **Pros:**

- ✅ **Solves key distribution** - Public keys can be shared freely
- ✅ **Digital signatures** - Prove identity
- ✅ **Scalable** - Work with many people

### **Cons:**

- ❌ **SLOW** - 100-1000x slower than symmetric
- ❌ **Complex** - Harder to implement

**Use case:** SSL/TLS (HTTPS), Bitcoin, secure email
