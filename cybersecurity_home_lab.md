## Cybersecurity Home Lab Setup
I designed this Cybersecurity Home Lab to serve as a personal training ground for hands-on learning and practical experience in cybersecurity. It’s a versatile lab equipped to simulate real-world environments for testing and analysis, using the following components:

- pfSense: Acts as the firewall and router to manage network traffic and enforce security policies.
- Kali Linux: A penetration testing platform for simulating and testing various attack scenarios.
- Metasploitable: A deliberately vulnerable virtual machine to practice exploitation techniques.
- Ubuntu Server and Desktop VMs: Used for hosting applications and running secure development tests.
- Windows 10: A typical client system for analyzing malware and testing exploits.

---

#### **Objective**
To build a fully functional cybersecurity home lab for penetration testing, firewall management, vulnerability assessment, and ethical hacking, using pfSense as a firewall and managing network traffic between three zones: WAN, LAN, and DMZ.

#### **End Goal**
1. Configure a secure and segmented network with pfSense acting as the firewall.
2. Use Kali Linux for offensive security tasks.
3. Use Windows 10 and Ubuntu 20.04 as client machines for testing exploits.
4. Use Metasploitable as a vulnerable machine to simulate attacks.
5. Gain practical skills in network security, vulnerability assessment, and system hardening.

---
### **Prerequisites**
- A computer with at least **16 GB RAM**, a **i5/i7 processor**, and **350 GB free storage**.
- Virtualization software: **VirtualBox**

- ISO images for:
  - **pfSense** (firewall).
  - **Kali Linux**.
  - **Windows 10**.
  - **Ubuntu 20.04**.
  - **Metasploitable**.
- Basic knowledge of networking and virtualization.

---
![VM Machine](https://github.com/user-attachments/assets/582c91b0-9595-43d7-a7e5-f281f7568d76)

![VM Machine](https://github.com/user-attachments/assets/43391977-bbed-46a6-958c-3f8115a33a2d)

### **Step 1: Install Virtualization Software**
1. Download and install **VirtualBox** on host machine.
2. Enable virtualization in the system BIOS/UEFI if not already done.

---

### **Step 2: Set Up pfSense**
1. Create a new VM in your virtualization software for **pfSense**:
   - Allocate **2 GB RAM**, **20 GB storage**, and **3 network adapters**.
   - Attach the **pfSense ISO image** to the VM.
2. Configure the network adapters:
   - **Adapter 1 (WAN)**: Connected to **NAT** (for external internet access).
   - **Adapter 2 (LAN)**: Connected to **Internal Network LAN**.
   - **Adapter 3 (DMZ)**: Connected to **Internal Network DMZ**.
3. Boot the pfSense VM and complete the installation:
   - Assign **WAN, LAN, and DMZ interfaces** during setup.
   - Set IP ranges for each interface:
     - WAN: Use DHCP for external IP: **10.0.2.15/24**
     - LAN: **192.168.1.1/24**.
     - DMZ: **192.168.2.1/24**.
4. Access the pfSense web GUI by entering the LAN IP (**192.168.1.1**) in a browser.

---

### **Step 3: Set Up the Client VMs**
#### **Kali Linux**
1. Create a new VM for **Kali Linux**:
   - Allocate **2 GB RAM** and **20 GB storage**.
   - Attach the **Kali Linux ISO image**.
2. Connect the network adapter to **Internal Network LAN**.
3. Install Kali Linux and update it (`sudo apt update && sudo apt upgrade`).

#### **Windows 10**
1. Create a new VM for **Windows 10**:
   - Allocate **2 GB RAM** and **20 GB storage**.
   - Attach the **Windows 10 ISO image**.
2. Connect the network adapter to **Internal Network LAN**.
3. Complete the installation and configure basic settings.

#### **Ubuntu 20.04**
1. Create a new VM for **Ubuntu 20.04**:
   - Allocate **2 GB RAM** and **20 GB storage**.
   - Attach the **Ubuntu 20.04 ISO image**.
2. Connect the network adapter to **Internal Network LAN**.
3. Install and update Ubuntu (`sudo apt update && sudo apt upgrade`).

#### **Metasploitable**
1. Create a new VM for **Metasploitable**:
   - Allocate **512 MB RAM** and **10 GB storage**.
   - Use the Metasploitable pre-configured virtual disk.
2. Connect the network adapter to **Internal Network LAN**.

---

### **Step 4: Configure pfSense**
1. **Create Firewall Rules**:
   - Allow **LAN-to-WAN traffic**.
   - Block **DMZ-to-LAN traffic**.
   - Allow **DMZ-to-WAN traffic**.
2. **Set Up NAT**:
   - Configure port forwarding for specific services (e.g., SSH, HTTP).
3. **Enable DNS and DHCP**:
   - Assign dynamic IPs for LAN and DMZ clients.

---







What I’ll Use the Lab For
1. Network Security Testing
Firewall Configuration: Fine-tune firewall rules on pfSense to allow or block traffic based on security needs.
Traffic Analysis: Use Security Onion to monitor traffic flow and identify potential threats in real time.
Intrusion Detection and Prevention: Test how effectively Security Onion detects and prevents simulated attacks.
2. Ethical Hacking and Penetration Testing
Exploitation Practice: Launch attacks from Kali Linux against Metasploitable to explore vulnerabilities.
Web Application Security: Host web applications on the Ubuntu Server and test for weaknesses using tools like Burp Suite.
Password Cracking: Test weak credentials using Hydra, John the Ripper, or other tools.
3. Malware Analysis
Behavior Analysis: Execute malware samples in the Windows 10 VM to observe their behavior safely.
Network Communication Analysis: Monitor malware’s network activity using Security Onion to understand its reach.
4. Vulnerability Assessment
Scanning: Use Nessus or OpenVAS to identify vulnerabilities in all systems.
Patch Testing: Test system updates or patches and validate their effectiveness in mitigating risks.
5. Forensics and Incident Response
Log Analysis: Use Security Onion to collect logs from pfSense and VMs, analyzing them for suspicious activity.
Network Forensics: Examine packet captures (PCAPs) for signs of network breaches.
Disk Forensics: Analyze compromised systems using tools like Autopsy.
6. Secure Development and Testing
Application Hardening: Test secure coding practices by hosting web applications on Ubuntu.
Dynamic Analysis: Use OWASP ZAP or similar tools to test application responses to simulated attacks.
7. Real-World Attack Simulations
Man-in-the-Middle (MITM) Attacks: Simulate MITM attacks to understand their impact and how to defend against them.
Phishing Campaigns: Set up email servers to practice and analyze phishing techniques.
Denial of Service (DoS) Testing: Simulate DoS attacks on isolated systems to evaluate their resilience.

Benefits of This Lab
Hands-On Learning: It provides a safe, controlled environment to practice cybersecurity concepts without risking production systems.
Skill Development: Enables me to refine my skills in penetration testing, forensics, malware analysis, and network security.
Portfolio Building: Projects and findings from the lab can be documented and showcased as proof of my practical experience.
Certification Preparation: The lab is ideal for preparing for certifications like CEH, OSCP, CompTIA Security+, and more.

Real-World Scenarios: By simulating real-world attacks, I’ll gain insights into how breaches occur and how to mitigate them.
Tool Mastery: Provides hands-on experience with industry-standard tools like pfSense, Kali Linux, and Metasploit.


### **Skills Gained**
   - Proficiency in configuring and managing pfSense for traffic control, NAT, and DHCP.  
   - Expertise in implementing firewall rules to secure segmented networks (LAN, WAN, DMZ).  
   - Designing secure networks with multiple interfaces.  
   - Practical understanding of network segmentation to mitigate threats.      
   - Building and managing virtualized environments with VMware or VirtualBox.  
   - Optimizing resource allocation for multi-VM setups.  
   - Diagnosing configuration errors and implementing effective solutions.  
    - Developing workflows for conducting cybersecurity assessments.  


This lab represents my commitment to becoming a well-rounded cybersecurity professional. If you’re interested in replicating this setup or need advice on specific configurations, feel free to reach out. Together, we can grow our skills and make cyberspace safer!
