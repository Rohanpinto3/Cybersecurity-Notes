# **Hashing and Digital Signatures**

---

## **Hashing (One-Way Street) 🛣️**

### **What it is:**

- **Convert data** → fixed-size string (hash)
- **One-way function** - Cannot be reversed
- **Like:** Putting meat through grinder → can't get original meat back

### **Properties:**

- **Deterministic** - Same input = same hash
- **Fast to compute**
- **Small change** = completely different hash
- **Collision resistant** - Hard to find two inputs with same hash

## **Digital Signatures (Electronic Seal) 🏛️**

### **What it is:**

- **Prove:** Who sent it + message wasn't modified
- **Like:** Wax seal on ancient letter

### **How it works:**

### **Signing:**

1. **Hash the message** → get message digest
2. **Encrypt hash** with your **private key** → signature
3. **Send** message + signature

### **Verification:**

1. **Decrypt signature** with sender's **public key** → get original hash
2. **Hash received message** → get new hash
3. **Compare** - if match → authentic! ✅
