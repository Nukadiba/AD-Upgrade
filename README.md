# Active Directory Domain Controller Migration  
### Windows Server 2008 R2 → Windows Server 2019  
**Domain:** 3lineng.com  
**Year:** 2025  

---

## 📌 Project Overview

This project documents the successful migration of an Active Directory Domain Controller from **Windows Server 2008 R2** to **Windows Server 2019**, including FSMO role transfer, LDAP integration with FortiGate, and VPN authentication validation.

The goal was to modernize the infrastructure, improve security, and enable centralized authentication for network access.

---

## 🏗 Environment Details

| Component | Description |
|------------|-------------|
| Legacy DC | Windows Server 2008 R2 |
| New DC | Windows Server 2019 |
| Domain | 3lineng.com |
| FSMO Roles | Successfully transferred to 2019 DC |
| Firewall | FortiGate |
| Authentication Method | LDAP (Active Directory) |

---

## 🚀 Implementation Steps

### 1️⃣ Deploy Windows Server 2019 Domain Controller

- Installed Windows Server 2019
- Configured static IP and DNS settings
- Installed **Active Directory Domain Services (AD DS)**
- Promoted server to Domain Controller
- Verified DNS functionality and replication health

---

### 2️⃣ Transfer FSMO Roles

Transferred all 5 FSMO roles to the new 2019 DC:

```powershell
Move-ADDirectoryServerOperationMasterRole -Identity "NEW-DC" -OperationMasterRole 0,1,2,3,4


