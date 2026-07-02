
# Packet Sniffing Lab

---

if you're  OS doesn't have wireshark pre-installed then install wireshark 

```bash
sudo apt install wireshark
```

wireshark is **packet analyzer** that lets you see every detail of what's happening on your network.

It’s like a **"microscope" for network traffic.**

### **What It Shows You:**

- **Every packet** traveling through your network
- **Source/Destination** IP addresses and ports
- **Protocols** being used (HTTP, DNS, SSH, etc.)
- **Full content** of unencrypted communications (passwords, files, messages)
- **Timing** and **conversations** between devices

---

### **Simple Analogy:**

- **Network Cable** = A highway
- **Data Packets** = Cars on the highway
- **Wireshark** = A police camera that records every car, where it came from, where it's going, and what's inside

  then run it up & it need sudo privilege  to run 

```bash
sudo wireshark 
```

ok now make a directory “i made hackme(thats where ymal file was stored from previous lab)” directory and then spin up docker 

```bash
sudo docker compose up
```

copy the  1st Ip address which is you're local machine Ip address 

then open wireshark and click to loopback and activate it by pressing on fin logo if not activated. now paste that ip address on to your browser and login with usr & pswd so you can send some traffic to that website and let  wireshark captre that traffic, 

and it would look something like this :

<img width="1918" height="878" alt="parrot_os_2 0-2025-11-08-23-16-58" src="https://github.com/user-attachments/assets/399ebced-bb60-4865-aef1-870a9e903d3e" />
you can even see the usr name & pswd 

the End this was just a practice lab.
