# Enterprise-Network-Security-Design

## Objective

  Create and propose a secure merged enterprise network.

## Skills Learned

  - Network Segmentation & VLANs
  - Network Security architecture
  - Zero Trust Architecture
  - Cloud Security & Disaster Recovery 
  - Vulnerability Assessment & Risk Analysis

## Vulnerabilities

### Company A: Network Security Problems 

1. Open ports 21-90 and 3389. These ports are mostly unsecure and should be closed if they are unused. Attackers could utilize these ports to get into the network in causing major issues. Strict firewall rules should be implemented to close the unused ports. 

2. Unused user accounts that are not decommissioned are a great danger to any company. Attackers will be able to exploit them and gain unauthorized access. Especially if there are not extensive password policies. This in turn increases the attack surface. Accounts should be decommissioned as soon as the personnel are relieved of duty.  

### Company A: Infrastructure Problems 

1. End of life (EOL) equipment being in use increases the organizations' attack surface greatly. EOL hardware no longer receives security updates, which makes it vulnerable to known exploits. The company should update the infrastructure to the current. 

2. The company is utilizing a single firewall; this introduces a single point of failure. If the firewall fails, the company could lose connectivity and/or security protections. The company should implement a second firewall in a high availability configuration to eliminate the single point of failure.  

### Company B: Network Security Problems  

1. There is an excess of open ports on the companies' network. Ports such as Telnet (23) and RDP (3389) make the network vulnerable to brute force attacks and unauthorized remote access. Any unused and unsecure ports immediately be closed. 

2. Multi-factor authentication (MFA) is not being enforced across all users of the organization. Without MFA, any compromised credentials could allow attackers to gain unauthorized access to its systems. MFA should be implemented for all remote access, admin accounts, and privileged systems. 

### Company B: Infrastructure Problems  

1. A single ISP router that connects the organization to the internet introduces a single point of failure. If the router fails, internet connectivity and access to services will be interrupted.  

2. There are virtualized servers, but it is not indicated that there is any high availability or disaster recovery. A server failure could take business critical services offline. High availability should be configured with regular backups also being conducted. 

 

## SECTION B: Existing Vulnerabilities, Impacts, and Risks. 

### Company A: 

B1. 	All users use eight-character passwords 

B2. 	Impact: Eight-character passwords increase the risk of passwords being cracked by brute-force attacks. 	If an attacker were able to obtain valid credentials, they would gain access to sensitive items and data. 

Risk: High 

Likelihood: High 

B1. 	Regular password changes are not enforced 

B2.	Impact: Without a regular password change policy, compromised or weak passwords may stay in use 	for long periods of time. This increases the chances of unauthorized access	.  

Risk: High 

Likelihood: Moderate 

### Company B: 

B1. 	Distributed Ruby (dRuby/DRb) Multiple Remote Code Execution Vulnerabilities 

B2.	Impact: Successful exploits allow attackers to execute arbitrary code on the affected machine. This 	could result in complete system compromise, data theft, or a disruption of critical services. 

Risk: High 

Likelihood: High 


B1. 	Operating System (OS) End of Life (EOL) Detection 

B2.	Impact: EOL operating systems no longer receive security updates. This leaves known vulnerabilities 	unaddressed in turn increasing the risk for unauthorized access, malware infections, and compliance 	issues. 

Risk: High  

Likelihood: High

## Steps

The proposed topology includes the following: 

- Zero Trust Architecture 
- Next-Generation Firewall (NGFW) 
- Hybrid Architecture with on-premises and Microsoft Azure 
- Demilitarized Zone (DMZ) 
- VPN with Multi-Factor Authentication (MFA) 
- VLAN Segmentation 
- Removal of end-of-life systems 
- Adds cloud backups, disaster recovery and centralized monitoring with Azure Sentinel 
- Keeps existing security tools to stay within $50,000 budget 
- Includes a Site-to-Site VPN 

<img width="1040" height="773" alt="Screenshot 2026-07-16 160052" src="https://github.com/user-attachments/assets/b33e5835-d821-44eb-b07b-67457ed8afc2" />

## Network Components

Internet/ISP Routers 

Next-Generation Firewalls (Fortigate)  

DMZ Web Server  

Reverse Proxy / WAF  

VPN Gateway  

Core Layer 3 Switches 

Distribution Switches 

Access Switches 

Servers (DC, File, App, DB, etc.) 

User/Client Devices 

Microsoft Azure Services 

## SECTION E: Rationale 

## Added 

### Component - Purpose / Rationale 

DMZ - Isolates public facing systems  

High Availability Firewalls and Switches - Adds redundancy for critical systems 

VPN with MFA  - Secures remote access  

VLAN Segmentation - Limits lateral movement 

Microsoft Azure Services - Backups, disaster recovery, and centralized monitoring 

Site-to-Site VPN - Connects on-premises machines to Azure securely 

## Repurposed / Retained 

### Component - Purpose / Rationale 

FortiGate NGFWs - Upgraded licensing, reused hardware, saving costs 

Security Tools - Tools such as DUO, Akami, Mimecast, etc. Will be retained to stay within budget 

Servers - Existing hardware will be reused where possible, they will be upgraded and hardened 

## Removed 

### Component - Purpose / Rationale 

End-of-Life OS - Windows Server 2012/2012 R2, Windows XP, Windows 7. 

Legacy Exchange Servers - Replaced with supported Exchange Server 2019  

Insecure Services and Protocols - Removed FTP, rexec, rsh, rlogin, anonymous FTP, etc. 

Direct RDP from Internet - Replaced with VPN + MFA 

## Breakdown

This design emphasizes and prioritizes the importance of repurposing and reutilizing the existing hardware to save cost. Doing this while investing in cloud to enhance security and improve the disaster recovery plan is crucial to keeping the business at its maximum operational speeds. This approach improves the confidentiality, integrity, and availability of the data, whilst keeping the first-year costs under $50,000. (Full Cost Breakdown pg. 8)

## SECTION F: Secure Network Design Principles 

A major principle that secures the network topology is the Zero Trust security model. This model requires all users and devices to authenticate before accessing the networks' resources. Remote users must connect through a VPN with MFA. Network segmentation and least privilege ensure users only have access to the resources necessary for their role. 

Another principle that secures the network is Network Segmentation. The enterprise network is divided into separate VLANs for servers, users, guests, printers, and management. Segmentation limits the lateral movement that an attacker can perform if they compromise a device. It prevents unauthorized access between the different segments. 

## SECTION G: Regulatory Compliance  

Payment Card Industry Data Security Standard (PCI DSS) is a relevant compliance standard because Company A processes financial transactions and Company B accepts credit card payments from its customers. Because of this, the merged organization must hold and protect cardholder data and maintain a secure environment for storing, processing, and transmitting payment information. 

The topology supports PCI DSS with the implementation of numerous security controls that protect cardholder data. The Demilitarized Zone isolates public facing servers from the internal network, while the Next-Gen Firewalls filter and monitor network traffic. VLAN segmentation increases security by separating critical and sensitive systems on the network from user and guest networks. This reduces the likelihood of unauthorized access.   

Health Insurance Portability and Accountability Act (HIPAA) is a relevant compliance standard because Company B designs and develops software for medical providers. That software likely stores, processes, or transmits protected health information (PHI). Because of this, the merged organization must implement administrative, physical, and technical safeguards to protect patient information.  

The topology supports HIPAA with the implementation of a Zero Trust Architecture. The Zero Trust requires that all users and devices must authenticate before accessing company resources. VPN access joined with Multi-Factor Authentication (MFA) increases the security of remote access to systems containing PHI. VLAN segmentation increases security by separating critical and sensitive systems on the network from user and guest networks. The DMZ and NGFWs also provide extra security for public facing services. While Microsoft Sentinel provides a place to monitor any suspicious events/incidents. Finally, Azure Backups provide disaster recovery and secure backups to improve the availability of healthcare data.  

## SECTION I: Summary

### First-Year Cost Breakdown ($50,000 Budget) 

Component - Purpose - Estimated Cost  

Windows Server 2022 Licenses (2) - Upgrade End of life servers - $3,000 

FortiGate 800D Licensing (2) - NGFW, IPS, App Control, Updates - $6,000 

DUO MFA (Additional Users) - VPN + MFA for all users - $2,500 

Azure Backup - Cloud Backups - $2,000 

Azure Site Recovery - Disaster Recovery - $2,000 

Microsoft Sentinel (SIEM) - Centralized Monitoring - $3,500 

Azure Storage - Secure Cloud Storage - $1,000 

Site-to-Site VPN Setup - Secure hybrid connectivity - $1,500 

Reverse Proxy / WAF (Akami) - Protect web servers/applications - $3,500 

Network Segmentation (VLANs) - Security Segmentations - $2,500 

Server Migration & Hardening - Migrate & secure systems - $8,000 

Security Awareness Training - Employee training - $2,500 

IT/Admin Technical Training - Training in Azure, Sentinel, and FortiGate - $3,000 

Documentation & Testing - Testing, Validation, Docs - $2,000 

### Total First Year Estimated Cost (USD) - $ 44,500 
### Remaining Budget: $5,500 (Contingency) 

The proposed network design remains in the budget of $50,000. This is accomplished by reusing existing hardware and infrastructure where it is serviceable. That includes FortiGate firewalls, DUO MFA, Mimecast, etc.  

The funds were primarily used to remove and upgrade end-of-life systems by implementing a hybrid cloud environment, and strengthening security through Sentinel, Azure Backup, and Site Recovery. Investing in security enhancements such as VLAN segmentation, server migration, and overall hardening also addresses the vulnerabilities found during the assessments and improves the security posture of the company.  

Employee security awareness and IT administrator training are necessary to help ensure the new resources and technologies are used effectively and securely.    

The remaining $5,500 contingency provides flexibility for unexpected issues or costs.  

The proposed budget and topology provide a cost-effective balance for enhancing security, increasing redundancy, and supporting the organizations' growth while staying within the financial parameters. 
