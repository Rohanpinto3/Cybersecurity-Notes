
### Wireless Attacks 


more and more devices use wireless protocol 

## these are :

- Wifi (802.11x)
- Cellular ( 4G, LTE, 5G,etc)
- Bluetooth
- Lora
- NFC
- Wireless attacks and defenses share overlaps with network-based attack ex: (packet sniffing )
- the properties of wireless networks presents new attacks  vectors and methods

---

# Wifi Protocol

---

## **1. WEP (Wired Equivalent Privacy)**

- **Status:** **BROKEN** - easily cracked in minutes
- **Flaw:** Weak encryption (RC4 stream cipher)
- **Attack:** Capture enough packets → crack key
- **Tools:** `aircrack-ng`, `wifite`

## **2. WPA/WPA2-PSK (Personal)**

- **Status:** **VULNERABLE** to brute force
- **Flaw:** Uses pre-shared key (your WiFi password)
- **Attack:** Capture handshake → brute force password
- **Tools:** `aircrack-ng`, `hashcat`

## **3. WPA-Enterprise**

- **Status:** **MORE SECURE** (when properly configured)
- **Uses:** RADIUS server + individual user logins
- **Attack:** Complex (certificate spoofing, PEAP attacks)
- **Security:** Each user has unique credentials

## **4. WPA3**

- **Status:** **MODERN SECURE**
- **Features:**
    - Simultaneous Authentication of Equals (SAE)
    - Forward secrecy
    - 192-bit encryption
- **Attack:** Very difficult (dragonblood vulnerabilities exist but rare)

<img width="1349" height="646" alt="image" src="https://github.com/user-attachments/assets/8c9a8722-1291-4022-8105-e012a485092d" />

