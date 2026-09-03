# Enterprise-Network-Security-Design

## Objective

  Create and propose a secure merged enterprise network.

### Skills Learned

  - Network Segmentation & VLANs
  - Network Security architecture
  - Zero Trust Architecture
  - Cloud Security & Disaster Recovery 
  - Vulnerability Assessment & Risk Analysis

## Vulnerabilities

Company A: Network Security Problems 

1. Open ports 21-90 and 3389. These ports are mostly unsecure and should be closed if they are unused. Attackers could utilize these ports to get into the network in causing major issues. Strict firewall rules should be implemented to close the unused ports. 

2. Unused user accounts that are not decommissioned are a great danger to any company. Attackers will be able to exploit them and gain unauthorized access. Especially if there are not extensive password policies. This in turn increases the attack surface. Accounts should be decommissioned as soon as the personnel are relieved of duty.  

Company A: Infrastructure Problems 

1. End of life (EOL) equipment being in use increases the organizations' attack surface greatly. EOL hardware no longer receives security updates, which makes it vulnerable to known exploits. The company should update the infrastructure to the current. 

2. The company is utilizing a single firewall; this introduces a single point of failure. If the firewall fails, the company could lose connectivity and/or security protections. The company should implement a second firewall in a high availability configuration to eliminate the single point of failure.  

Company B: Network Security Problems  

1. There is an excess of open ports on the companies' network. Ports such as Telnet (23) and RDP (3389) make the network vulnerable to brute force attacks and unauthorized remote access. Any unused and unsecure ports immediately be closed. 

2. Multi-factor authentication (MFA) is not being enforced across all users of the organization. Without MFA, any compromised credentials could allow attackers to gain unauthorized access to its systems. MFA should be implemented for all remote access, admin accounts, and privileged systems. 

Company B: Infrastructure Problems  

1. A single ISP router that connects the organization to the internet introduces a single point of failure. If the router fails, internet connectivity and access to services will be interrupted.  

2. There are virtualized servers, but it is not indicated that there is any high availability or disaster recovery. A server failure could take business critical services offline. High availability should be configured with regular backups also being conducted. 

 

SECTION B: Existing Vulnerabilities, Impacts, and Risks. 


Company A: 

B1. 	All users use eight-character passwords 

B2. 	Impact: Eight-character passwords increase the risk of passwords being cracked by brute-force attacks. 	If an attacker were able to obtain valid credentials, they would gain access to sensitive items and data. 

Risk: High 

Likelihood: High 

B1. 	Regular password changes are not enforced 

B2.	Impact: Without a regular password change policy, compromised or weak passwords may stay in use 	for long periods of time. This increases the chances of unauthorized access	.  

Risk: High 

Likelihood: Moderate 

Company B: 

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

