

# End Point Protection & Antivirus & lab

> *Your Digital Immune System*
> 

---

# what is an endpoint ?

An **endpoint** is any device that connects to your network which a human reacts with:

**Examples:**

- Laptops 💻
- Desktops 🖥️
- Servers 🗄️
- Phones 📱

In Endpoint protection, Software is downloaded on you're device and the device is monitored. 
• They're the **last line of defense** after network security.

**Think of it this way:**

- **Network security** (firewalls, IPS) = protecting the castle walls
- **Endpoint security** (EDR, antivirus) = protecting each individual room and person inside the castle

If an attacker gets past your firewall, endpoints are what they're trying to compromise.

---

# Two Types of Endpoint protection🔻

1. **Antivirus  (AV)**
2. Endpoint Detection & Response (EDR)

# **Antivirus  (AV)**

> A vaccine for your computer
> 

---

**What it does:**

- Scans files and programs for **known malicious code** (signatures)
- Blocks or quarantines anything that matches its database of threats

**How it works:**

1. Has a database of "bad guy" fingerprints
2. Checks every file against this database
3. If match found → blocks/removes the file

**Limitations:**

- Only catches **known** threats (like a wanted poster)
- Useless against new, unknown malware (zero-days)
- Mostly preventive, not good for investigation

**It's the basic hygiene** - necessary but not sufficient alone. That's why EDR was developed.

---

# **Signature & Signature based detection lab :**

A **signature** is like a **fingerprint** or **wanted poster** for malware.

**What it contains:**

- Unique patterns of code from known viruses
- Specific file hashes (MD5, SHA-256)
- Behavioral characteristics

**How it works:**

1. Antivirus has a database of thousands of malware signatures
2. It scans files looking for matches to these signatures
3. If it finds a match → "Found virus!" and quarantines the file

---

# THE LAB PART

Make a directory named Signature_lab then download a zip file called [malz.zip](https://uploads.teachablecdn.com/attachments/h1DLyM50RiumcnnTBXCK_malz.zip) , inside this zip there is an text file called text.exe which is revershelled (A malicious program that gives an attacker **remote control** of your computer). now unzip the zip file by the command 

```bash
unzip malz.zip
```

then follow up with password : infected

Now when you ls, you may see the texted file called text.exe. Now you will create a checksum 

**Checksum = The file's fingerprint.**

**What it does:**

- Creates a **unique hash** (string of characters) that identifies the file
- Even a tiny change in the file creates a completely different checksum

**Command to create it:**

bash

```
md5sum txt.exe
```

or

bash

```
sha256sum txt.exe
```

- **MD5:** Creates a 128-bit hash (32 characters)
- **SHA-256:** Creates a 256-bit hash (64 characters)

They use different mathematical formulas to calculate the fingerprint.

**Why both exist:**

- **MD5:** Faster, but less secure (can have collisions)
- **SHA-256:** Slower, but much more secure

In security, we prefer **SHA-256** because it's more unique. You're creating two different types of fingerprints for the same file.

once you get the hash copy, open browser and search [virus total](https://www.virustotal.com/gui/home/search) and paste the hash string and the website will show you How many antivirus engines recognize your hash as malicious.

<img width="1720" height="820" alt="image" src="https://github.com/user-attachments/assets/15e5dab5-524b-453a-bd7a-d1d50e01b1e4" />

---

# Endpoint Detection & Response (EDR) 🪇

---

**EDR = Endpoint Detection and Response**

Think of it as **24/7 CCTV + Security Guard** for every computer in your company.

**What it does differently from traditional Antivirus:**

| **Traditional Antivirus** | **EDR** |
| --- | --- |
| Scans files for known bad signatures | Records **every process, network call, file change** |
| "Is this file bad?" | "Why is this process behaving strangely?" |
| Prevents known threats | Investigates & hunts unknown threats |

**EDR Key Features:**

- **Timeline Recording:** Can replay exactly what happened during an attack
- **Behavior Analysis:** Spots unusual activity (e.g., "Word.exe suddenly spawning PowerShell")
- **Response:** Can remotely isolate infected machines, kill processes
- **Hunting:** Lets SOC analysts search across all company computers for threats

**How EDR Works:**

**1. Agent-Based:**

- Small software installed on each endpoint (laptop, server)
- **Agent** constantly monitors: processes, network, registry, memory
- Sends this data to a **cloud console**

**2. Cloud-Based Console:**

- Central brain that collects data from all agents
- Correlates events across your entire organization
- Uses AI to detect suspicious patterns
- SOC analysts login here to investigate & respond

**Flow:**

Endpoint → **EDR Agent** → **Cloud Console** → SOC Team

**Example:**

- Agent sees `word.exe` spawning `powershell`
- Cloud correlates this with 10 other computers doing the same
- **Alert:** "Potential phishing campaign in progress"
- SOC can remotely kill processes on all affected machines
