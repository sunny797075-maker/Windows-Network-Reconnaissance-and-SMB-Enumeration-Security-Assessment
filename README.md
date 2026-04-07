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

##2) smbclient

-  Purpose: SMB share interaction and access validation

-  smbclient was used to connect to SMB shares and test whether shared resources were accessible.

-  Why used:

- Lists available SMB shares
- Validates whether shares are accessible
- Helps inspect files and directories in exposed shares
- Useful for testing authentication and permissions

- Common usage:

- smbclient -L //<target-ip>/ -N
- smbclient //<target-ip>/<share-name>
##3) enum4linux

- Purpose: Windows and SMB enumeration

- enum4linux was used to collect information from the Windows SMB environment.

- Why used:

- Enumerates users and shares
- Identifies hostname, workgroup, and domain details
- Provides Windows-related information useful for security analysis
- Helps detect information disclosure risks

##Common usage:

- enum4linux -a <target-ip>

##4) Supporting Tools

- These tools can also support the project for deeper analysis:

- Wireshark – packet capture and SMB traffic analysis
- rpcclient – additional Windows RPC enumeration
- smbmap – SMB share and permission mapping
- CrackMapExec – advanced SMB enumeration in lab environments
- Nessus / OpenVAS – vulnerability assessment
- Netcat – basic connectivity testing
- Metasploit – validation of known SMB weaknesses in authorized labs only

##🔍 Methodology
- Step 1: Target Identification and Initial Reconnaissance

- The assessment began with initial reconnaissance to identify reachable hosts and discover exposed services in the target environment. Nmap was used to scan the system and detect open ports, active services, and protocol details.

- Step 2: Service Enumeration

- After identifying open ports, the next step was to analyze which services were running and determine whether any of them represented a meaningful attack surface. Special attention was given to SMB-related ports 139 and 445, since these are commonly associated with Windows file-sharing services.

- Step 3: SMB Share Enumeration

- Once SMB was identified, smbclient was used to interact with the SMB service. This helped determine:

- Whether shares were visible
- Whether anonymous access was allowed
- Whether files and directories inside shares were exposed
- Whether permissions appeared weak or misconfigured
- Step 4: Windows Environment Enumeration

- To gather more details about the target Windows system, enum4linux was used. This step focused on collecting:

- User information
- Share information
- Hostname details
- Workgroup or domain information
- Other Windows-related enumeration data
- Step 5: Analysis of Findings

- All collected results were reviewed to understand the attack surface and identify possible security concerns such as exposed services, information leakage, weak access control, and SMB-related weaknesses.

- Step 6: Documentation and Reporting

- The final step involved documenting all technical findings, potential risks, and recommended mitigation steps in a structured and clear format suitable for security reporting.

##🧩 Detailed Tool Role in the Project
Nmap Role in the Project

- Nmap played the role of the primary reconnaissance tool. It was used at the beginning of the assessment to map the target system's exposed network surface. By identifying open ports and services, Nmap helped determine which services required deeper investigation. In this project, its most important contribution was identifying SMB exposure on Windows-related ports.

- smbclient Role in the Project

- smbclient acted as the SMB interaction and validation tool. After Nmap indicated the presence of SMB services, smbclient was used to directly connect to the available shares. This made it possible to test visibility of shared resources, check whether anonymous access was allowed, and inspect whether exposed shares could reveal sensitive content.

##enum4linux Role in the Project

- enum4linux served as the Windows enumeration tool. Its role was to gather additional intelligence from the SMB environment, including users, shares, host details, and workgroup/domain information. It helped deepen the assessment by exposing information that could be useful for understanding the security posture of the Windows target.

- Supporting Tools Role

- Supporting tools such as Wireshark, rpcclient, smbmap, CrackMapExec, and Nessus/OpenVAS can strengthen the project by adding packet analysis, deeper enumeration, permission mapping, and vulnerability detection. These tools are useful when expanding the project beyond the basic workflow.

##📊 Key Findings
- Identified open ports and active services on the target Windows system
- Confirmed the presence of SMB-related services
- Enumerated accessible SMB shares
- Gathered host, share, and Windows-related information
- Observed possible information disclosure through SMB enumeration
- Determined that SMB was a key service requiring security attention
- ⚠️ Potential Risks Identified
- Unauthorized access to exposed SMB shares
- Information disclosure through user and share enumeration
- Weak or misconfigured SMB permissions
- Exposure of sensitive files or directories through accessible shares
- Increased attack surface due to unnecessary open ports and services
- Potential exploitation risk if insecure or legacy SMB configurations are enabled
- Greater risk of lateral movement in poorly secured Windows environments
- 🛡️ Recommendations
- Restrict SMB access to trusted users and systems only
- Disable anonymous SMB access unless specifically required
- Apply least-privilege permissions to shared folders
- Disable insecure legacy protocols such as SMBv1
- Close unnecessary ports and disable unused services
- Regularly patch Windows systems and related SMB services
- Monitor SMB access logs for suspicious activity
- Use firewall rules to limit exposure of ports 139 and 445
- Review share configurations to prevent unintentional data exposure
- 💡 Skills Demonstrated
- Network Reconnaissance
- Port Scanning
- Service Enumeration
- SMB Enumeration
- Windows Enumeration
- Attack Surface Analysis
- Vulnerability Assessment
- Security Documentation
- SMB Share Analysis
- Windows Environment Assessment
##📘 Learning Outcome

-This project provided practical experience in conducting a structured security assessment of a Windows-based SMB environment. It improved understanding of how reconnaissance tools identify exposed services, how SMB shares can be enumerated and analyzed, and how Windows-related information can be gathered through enumeration techniques. It also strengthened skills in attack surface analysis, risk identification, and security reporting.
