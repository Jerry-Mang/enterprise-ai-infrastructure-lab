## Overview

Built and configured a Windows Server 2019 Active Directory environment hosted on VMware ESXi to simulate a small business infrastructure. Implemented Active Directory Domain Services, DNS, DHCP, user administration, domain-joined workstations, and Group Policy management to replicate a real-world enterprise environment.

---

### Infrastructure
Hypervisor
- VMware ESXi

Server
- Windows Server 2019
- Domain Controller (DC1)

Client Devices
- WIN10-IT
- FIN01

Domain
- hq.lab.org
- 
---

### Core Services Implemented

Active Directory Domain Services (AD DS)

Installed and configured:

- Active Directory Domain Services
- Domain Controller promotion
- Forest creation
- Domain configuration

Domain:

hq.lab.org

### DNS Services

Configured DNS to support:

- Active Directory integration
- Domain name resolution
- Client workstation authentication
- Internal service discovery

Verified successful DNS resolution between domain controller and client workstations.

---

### DHCP Services

Configured DHCP scope for automatic IP allocation.

Implemented:

- DHCP scope creation
- Gateway assignment
- DNS server assignment
- Client lease validation

Verified client devices successfully obtained network configuration automatically.

Organisational Unit Structure

Created departmental OUs:

```text
HQ
├── HR
├── Finance
└── IT
```

Purpose:

- User organisation
- Group Policy targeting
- Departmental administration

---

### User Administration

Created domain user accounts including:


```text
HQ\adam.hr
HQ\rex.finance
```

Performed:

User account creation
Password assignment
Account management
Password reset procedures
User authentication testing
Security Groups

Created departmental security groups:

HR-Users
Finance-Users
IT-Users

Implemented group-based access control for shared resources.

Domain Join Operations

Successfully joined Windows 10 client workstations to Active Directory.

Domain-joined devices:

WIN10-IT
FIN01

Verified:

Domain authentication
Domain login
Computer object creation in Active Directory
DNS registration

Example domain login:

```text
HQ\rex.finance
Group Policy Management
```


Implemented Group Policy Objects (GPOs) to simulate enterprise endpoint management.

Configured:

Drive Mapping

Automatically mapped departmental network drives:

```text
H: HR Drive
F: Finance Drive
Endpoint Restrictions
```

Applied security policies including:

Control Panel restrictions
User environment lockdown
Centralised desktop management

Verified successful policy deployment using:

gpupdate /force
File Services

Created departmental shared folders:

```text
C:\Shares\HR
C:\Shares\Finance
C:\Shares\IT
```

Configured:

Share Permissions
NTFS Permissions
Security Group Access Control

Validated user access based on group membership.

---

### Skills Demonstrated

- VMware ESXi
- Windows Server 2019
- Active Directory
- DNS
- DHCP
- Domain Services
- User Administration
- Security Groups
- Group Policy
- Drive Mapping
- File Sharing
- NTFS Permissions
- Authentication
- Endpoint Management
- Windows 10 Enterprise Administration

---

### Outcome

Successfully deployed and managed a functional enterprise-style Active Directory environment supporting centralised authentication, departmental access control, Group Policy management, and domain-joined Windows client devices.
