# Methodology  
## Panther Identity Domain  
### Windows Server • Active Directory • Identity & Access Management

The Panther Identity Domain project demonstrates the deployment, configuration, and validation of a full Windows Server 2022 Active Directory environment. This includes provisioning a Primary Domain Controller (PDC), configuring DNS, promoting the domain, implementing organizational structure, and automating user creation using PowerShell. The goal of this project was to simulate real-world systems administration and identity management tasks while establishing a secure enterprise directory environment.

---

## 1. Project Scope & Objectives

This project focused on:

- Deploying Windows Server 2022 virtual machines  
- Configuring static IPv4 settings to enable domain operations  
- Installing and configuring Active Directory Domain Services (AD DS)  
- Promoting the server to a domain controller  
- Setting up DNS as part of domain creation  
- Creating Organizational Units (OUs)  
- Automating identity lifecycle using PowerShell  
- Validating domain functionality through connection and role testing  

This environment replicates the foundational components of enterprise identity and access management.

---

## 2. Environment Setup

Two Windows Server 2022 virtual machines were prepared:

### **Primary Domain Controller (PDC)**  
- Assigned static IPv4 address  
- Configured DNS to point to itself  
- Hostname set prior to promotion  
- Windows updates applied  

### **Secondary Systems (optional in future expansion)**  
- Additional server prepared for role additions or replication  
- Workstations may be joined later to demonstrate full domain membership  

---

## 3. Server Configuration & Network Preparation

Before installing AD DS, the following configuration steps were completed:

- Set static IP address  
- Assigned DNS server to the local server  
- Confirmed gateway and subnet mask  
- Verified hostname correctly set  
- Ensured connectivity via ping and server manager checks  

The server’s network reliability and naming were validated to avoid domain promotion errors.

---

## 4. Installing Active Directory Domain Services (AD DS)

Using Server Manager:

1. **Add Roles and Features**  
2. Select **Active Directory Domain Services**  
3. Include DNS Server as required by AD DS  
4. Validate dependencies  
5. Install roles  

Once installation completed, the system was ready for domain promotion.

---

## 5. Promoting the Server to a Domain Controller

The server was promoted using the Post-Deployment Configuration Wizard:

- Chose **Add a new forest**  
- Named the root domain  
- Set Directory Services Restore Mode (DSRM) password  
- Verified DNS delegation  
- Applied automatic configurations  
- Restarted after promotion  

After reboot, the server functioned as the primary domain controller (PDC).

---

## 6. DNS Configuration

DNS installation occurred automatically during promotion.  

Tasks validated included:

- Forward lookup zone creation  
- Domain zone replication  
- Host (A) record creation for domain controller  
- Confirmation of SRV records  

DNS was tested for resolution reliability, ensuring domain join functionality for future clients.

---

## 7. Organizational Units (OU) Structure

A logical OU hierarchy was created to support identity and device management.  
Examples included:

- Users  
- Computers  
- Admin Accounts  
- Service Accounts  

This structure supports role-based access, delegation, and GPO application.

---

## 8. PowerShell-Based User Creation

PowerShell scripts were used to automate identity provisioning.

Tasks included:

- Importing CSV files containing user details  
- Running scripts to bulk-create user accounts  
- Assigning usernames, passwords, and profiles  
- Placing users in correct OUs  
- Verifying account creation via ADUC and PowerShell  

This simulates real enterprise onboarding workflows.

---

## 9. Identity Validation & Testing

After domain configuration:

- Verified domain controller health using `dcdiag`  
- Confirmed replication components (if applicable)  
- Validated DNS resolution  
- Checked user authentication  
- Tested login capability for newly created accounts  

System stability and AD integrity were confirmed.

---

## 10. Lessons Learned

- Static IP configuration is foundational for domain reliability  
- Hostname and DNS alignment prevent AD promotion errors  
- PowerShell significantly improves IAM efficiency  
- DNS health directly affects domain operations  
- Proper OU design simplifies long-term management  

---

## Summary  

The Panther Identity Domain project simulates the deployment and administration of a real Active Directory environment. Through server configuration, AD DS installation, domain promotion, OU creation, and PowerShell automation, this project demonstrates strong competence in Windows system administration, identity management, and foundational enterprise IT operations.

