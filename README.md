# Elevate Labs Cyber Security Internship - Task 1

## 🎯 Task: Scan Your Local Network for Open Ports.

### 📝 Objective
The objective of this task is to learn how to discover open ports on devices within a local network to understand network exposure.

### 🛠️ Tools Used
*   **Nmap:** Used for performing network reconnaissance and port scanning.
*   **Kali Linux Terminal:** The environment used to execute commands.

---

### 🚀 Steps Performed

1.  **Identify Local Network Range:**
    *   Used the `ip a` command to find the local IP address and subnet mask.
    *   Identified the network range as `192.168.31.130/24` on the `eth0` interface.

2.  **Perform Initial TCP SYN Scan:**
    *   Executed a basic stealth SYN scan to discover live hosts and open ports using the command: `sudo nmap -sS 192.168.31.130/24 -T4`.

3.  **Perform Service Version Detection and Save Output:**
    *   Ran a more detailed scan with service version detection (`-sV`) and outputted the results to a text file using the `-oN` flag.
    *   Command used: `sudo nmap -sS -sV 192.168.31.130/24 -oN task-1.txt`.

4.  **Review the Output:**
    *   Used the `cat task-1.txt` command to read the generated file and analyze the discovered network exposure.

---

### 📊 Scan Results & Analysis
The scan successfully scanned 256 IP addresses in 214.80 seconds, identifying 3 active hosts on the network. 

**Key Findings:**
*   **Host 192.168.31.2:** Identified as a VMware machine. Port `53/tcp` is open, running the `Unbound` domain service.
*   **Host 192.168.31.254:** Identified as a VMware machine. All 1000 scanned ports are in ignored (filtered) states.
*   **Host 192.168.31.130 (Localhost):** All 1000 scanned ports are in ignored (filtered) states.
