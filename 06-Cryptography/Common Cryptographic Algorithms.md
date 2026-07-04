# **Common Cryptographic Algorithms**

## 

# **Encryption Algorithms**

Recall that encryption algorithms convert readable data called the plaintext into unreadable data called the ciphertext using a key (and usually an initialization vector). They are usually broken down into two different types. Symmetric, which uses the same key to both encrypt and decrypt, and Asymmetric which uses a separate key for encryption and decryption.

# **AES (Advanced Encryption Standard)**

Type: Symmetric

Status: Secure

Use cases: VPNs, full-disk encryption, TLS, encrypted messaging

Details: AES is the modern standard for symmetric encryption, supporting 128, 192, and 256-bit keys. Fast, secure, and hardware-accelerated on most modern CPUs. Used almost everywhere secure encryption is required.

# **DES (Data Encryption Standard)**

Type: Symmetric

Status: Broken

Use cases: Legacy only

Details: DES has a 56-bit key and is now insecure due to brute-force vulnerabilities. It was officially replaced by AES and should not be used in modern systems.

# **Triple DES (3DES)**

Type: Symmetric

Status: Weak / Deprecated

Use cases: Legacy banking systems, older hardware

Details: Applies DES encryption three times. More secure than DES but very slow and vulnerable. Deprecated in modern systems.

# **Blowfish**

Type: Symmetric

Status: Secure (but aging)

Use cases: File encryption, legacy systems, some VPNs

Details: A fast, flexible alternative to DES. Supports variable key lengths and 64-bit blocks. Still used in tools like Veracrypt but less suitable for large data due to small block size.

# **Twofish**

Type: Symmetric

Status: Secure

Use cases: Open-source tools, Veracrypt, file encryption

Details: Supports 128, 192, and 256-bit keys with 128-bit blocks. Secure and flexible, though not as widely used as AES.

# **RSA (Rivest–Shamir–Adleman)**

Type: Asymmetric

Status: Secure (with large key sizes)

Use cases: Key exchange, digital signatures, TLS

Details: Uses large prime numbers and factoring. Still common for signing and encrypting keys. Slow for bulk data; minimum recommended key size is 2048 bits.

# **ECC (Elliptic Curve Cryptography)**

Type: Asymmetric

Status: Secure

Use cases: TLS, mobile apps, cryptocurrencies

Details: Offers high security with small keys, making it fast and efficient. Used in ECDSA (signatures) and ECDH (key exchange).

# **Diffie-Hellman / ECDH**

Type: Asymmetric (key exchange only)

Status: Secure

Use cases: TLS, VPNs, secure key exchange

Details: Used to establish a shared symmetric key over an insecure channel. ECDH is the modern and secure variant using elliptic curves.

# **Hashing Algorithms**

Recall that encryption algorithms convert input data into a fixed-length digest hash. Hashing is one way and not used for encryption, but instead to ensure integrity. It is used in digital signatures, checksums and for storing password.

# **SHA-1 (Secure Hash Algorithm 1)**

Status: Broken

Use cases: Legacy systems only

Details: Vulnerable to collision attacks. Deprecated in most systems and should not be used for secure applications.

# **SHA-2 (e.g., SHA-256, SHA-512)**

Status: Secure

Use cases: TLS, digital signatures, file integrity, blockchain

Details: The current standard for general-purpose hashing. SHA-256 is widely used and collision-resistant.

# **SHA-3**

Status: Secure

Use cases: Alternative to SHA-2

Details: Based on Keccak. Designed with different structure to SHA-1/2. Secure and future-ready, though not yet widely adopted.

# **MD5**

Status: Broken

Use cases: Non-security checksum only

Details: Widely broken and should never be used for security. Vulnerable to fast collision attacks.

# **bcrypt**

- Status: Secure
- Use cases: Password hashing
- Details: Includes salting and is deliberately slow to resist brute-force attacks. Still widely used and recommended for password storage.

# **scrypt / Argon2**

Status: Secure

Use cases: Password hashing

Details: Designed to be CPU- and memory-intensive to slow down cracking. Argon2 is the winner of the Password Hashing Competition and is recommended for new systems.

# **TL;DR - This is the most important details**

- Use **AES** or **Twofish** for secure symmetric encryption.
- Use **RSA** or **ECC** for key exchange and digital signatures.
- Use **SHA-2** or **SHA-3** for hashing.
- Use **bcrypt**, **scrypt**, or **Argon2** for the most secure password storage.
- Avoid **DES**, **3DES**, **MD5**, and **SHA-1** in any new or secure systems
