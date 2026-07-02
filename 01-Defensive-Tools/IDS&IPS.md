
# IDS & IPS

INTRUSION DETECTION SYSTEM & INTRUSTION PREVENTION SYSYTEM 

---

# **IDS (Intrusion Detection System):**

- Like a security camera
- **Job:** Watches traffic and **alerts** you when it sees something bad.

it alerts the soc analyst by detecting any malicious activity via sending a waring or a text message or etc. 

---

# **IPS (Intrusion Prevention System):**

- Like a security guard.

• **Job:** Watches traffic and **actively blocks** attacks.

IPS doesn't just alerts but it responds to the incident by preventing it from happening by blocking or cutting of specific network traffic  

---

- IDS & IPS can be host based or network based and also virtual
- most commonly it is just used network based

### **Practical Tools to Know**

- **Suricata** (Modern, high-performance)
- **Snort** (The classic, very established)
- **Security Onion** (A whole Linux distro packed with IDS/IPS tools)

---

# HOW DO IDS & IPS WORK :  🤔

# Intrusion Detection System(IDS) :

![image.png](image.png)

network traffic come through the internet to the router and then firewall then to the switch, switch will mirror a copy and sends the traffic to the destination. NOW if this was some malicious traffic which was missed out by the firewall and something bad happens to the computer then picked up by the IDS it will send an alert whether it is an email or a text message or through the SIEM tool. 

now someone must receive that message and come check the host computer  and remove it manually 

- **The Weakness:** This is **reactive security**. The damage might already be done before you respond.
- **That's why IPS was created** - to automatically block threats instead of just alerting.

# Intrusion Prevention System(IPS) :

![image.png](image%201.png)

network traffic come through the internet to the router and then firewall then pass through IPS 

and to the host computer which is inline with the IPS, NOW lets  say something bad happen and the traffic turns out to be an malicious traffic THEN it gets picked up by the IPS and not only it sends an alert, it can be configured to cut of the network of the host.
