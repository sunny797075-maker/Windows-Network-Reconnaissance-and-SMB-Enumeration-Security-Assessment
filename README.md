<img width="612" height="421" alt="image" src="https://github.com/user-attachments/assets/94a2137f-b087-4a20-9c7d-bdc51a7585a3" />

# Windows Network Reconnaissance and SMB Enumeration Security Assessment

## 📌 Overview
This project demonstrates a security assessment of a **Windows-based network file-sharing environment**. The objective was to perform **network reconnaissance**, identify **open ports and active services**, and enumerate the **SMB service** to gather critical information about the target Windows environment.

---

## 📚 Table of Contents
- [Overview](#-overview)
- [Problem Statement](#-problem-statement)
- [Task to be Completed](#-task-to-be-completed)
- [Project Description](#-project-description)
- [Tools Used](#-tools-used)
- [Methodology](#-methodology)
- [Key Findings](#-key-findings)
- [Skills Demonstrated](#-skills-demonstrated)
- [Resume Version](#-resume-version)
- [GitHub About Description](#-github-about-description)
- [Disclaimer](#-disclaimer)

---

## 🎯 Problem Statement
As a cybersecurity analyst entrusted with evaluating the security landscape of a client's network, initial investigations revealed potential vulnerabilities in the network's file-sharing service. The mission was to conduct comprehensive network reconnaissance, identify open communication channels and running services, and further analyze the SMB-based file-sharing infrastructure to gather critical insights about the target Windows environment.

---

## ✅ Task to be Completed
- Perform exhaustive network reconnaissance using **Nmap**
- Identify **open ports** and **active services**
- Document scan findings and determine possible targets for deeper enumeration
- Focus on **SMB service analysis** based on Nmap results
- Use **smbclient** to connect with SMB shares
- Use **enum4linux** to gather information about the target **Windows environment**
- Document security risks and possible remediation steps

---

## 🧾 Project Description
Performed network reconnaissance and SMB enumeration in a Windows-based environment using **Nmap**, **smbclient**, and **enum4linux** to identify open ports, active services, SMB shares, and Windows host information. Assessed attack surfaces, identified security risks, and documented findings with remediation recommendations.

---

## 🛠️ Tools Used

## 1) Nmap - Network Mapper
**Purpose:** Network reconnaissance and port scanning

Nmap was used to perform the initial scan of the target system and identify:
- Open ports
- Running services
- Service versions
- SMB-related ports such as **139** and **445**

**Why used:**
- Helps discover the attack surface
- Identifies possible entry points
- Supports service fingerprinting and enumeration planning

**Common usage:**
```bash
nmap -sV <target-ip>
nmap -A <target-ip>
