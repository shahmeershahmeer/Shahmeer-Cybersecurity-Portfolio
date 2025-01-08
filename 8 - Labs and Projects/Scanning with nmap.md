# Host Scanning with Nmap

## Introduction
Nmap (Network Mapper) is a widely used tool for network scanning, employed by both hackers and system administrators to discover critical information about a target system or network.

## Lab Objective
Learn how to scan a host using Nmap and understand the results.

## Lab Purpose
Nmap is an essential tool for gathering information about hosts, such as:
* Devices connected to a network
* Open ports on a device
* Services running on open ports
* Device uptime
* Firewall presence and configuration

By using Nmap, system administrators can strengthen security, and ethical hackers can identify vulnerabilities.

## Lab Environment
### Required Tools
* **Kali Linux**: Use Kali Linux as the operating system for conducting this lab

### Lab Topology
* Use Kali Linux in a virtual machine
* Target site: `scanme.nmap.org` (provided by Nmap for public scanning purposes)

> **Note**: Always obtain permission before scanning any site, system, or network that you do not own.

## Lab Walkthrough

### Task 1: Basic Nmap Scan
1. Open a terminal in Kali Linux
2. Run the command:
```bash
nmap scanme.nmap.org
```
<img width="625" alt="Screenshot 2025-01-06 at 1 40 49 PM" src="https://github.com/user-attachments/assets/2ad7f313-0a60-4064-96b2-2242f30e61ad" />

3. Observe the results:
   * Open ports and associated services will be displayed
   * This is a basic scan limited to the top 1000 ports for essential information

**Expected Output:**
* The scan should reveal multiple open ports and the services running on them
* Example: HTTP on port 80

### Task 2: Advanced Nmap Scan
In this step, you will retrieve more detailed information about the target, such as:
* Service versions
* Operating system details

#### Steps:
1. Attempt the following command:
```bash
sudo nmap -v -sT -sV -O scanme.nmap.org
```
<img width="808" alt="Screenshot 2025-01-06 at 2 46 36 PM" src="https://github.com/user-attachments/assets/a461ea6e-c002-4af3-86a2-c3b76669c5d4" />

#### Analysis:
* The output will include:
   * Exact versions of the software running on open ports
   * Operating system version and other system details

> **Note**: Firewall presence might restrict the visibility of some details.

#### Alternative Method:
* Use the `-A` flag for a comprehensive scan:
```bash
sudo nmap -A scanme.nmap.org
```
<img width="787" alt="Screenshot 2025-01-06 at 2 46 54 PM" src="https://github.com/user-attachments/assets/77d66cb8-1c7d-4577-bb99-81fd45dd4b67" />

### Task 3: Experimenting with Nmap Flags
1. Explore different scan types and their outputs using flags
2. Refer to the official Nmap documentation for flag details: [Nmap Port Scanning Options](https://nmap.org/book/port-scanning-options.html)

#### Example Commands:
* **Scan all ports:**
```bash
sudo nmap -p- scanme.nmap.org
```

* **Aggressive scan:**
```bash
sudo nmap -A scanme.nmap.org
```

* **UDP scan:**
```bash
sudo nmap -sU scanme.nmap.org
```

* **Ping scan (to check if the host is up):**
```bash
sudo nmap -sn scanme.nmap.org
```

## Key Takeaways
* Nmap is a versatile and powerful tool for network scanning
* Basic scans provide a quick overview, while advanced scans yield detailed information about services, ports, and operating systems
* Always adhere to ethical guidelines and obtain proper permissions when using Nmap
