# VMware ESXi Enterprise Infrastructure Lab

## Overview

## Environment

### Physical Host
- Dell T110 II
- Intel Xeon E3-1220 v2
- VMware ESXi

### Virtual Machines
- Windows Server 2019
- Windows 10 IT Workstation

## Virtual Network Design

## Active Directory Integration

### Domain Join
### User Authentication
### Domain Login Testing

---

## Storage Expansion

### Initial State
130GB Virtual Disk

### Expansion
Objective

Increase available storage capacity on the VMware ESXi host by creating and expanding a VMFS datastore using a dedicated 500GB SATA hard disk.

| Component      | Details                   |
| -------------- | ------------------------- |
| Host Server    | Dell T110 II              |
| Hypervisor     | VMware ESXi 6.5           |
| Storage Device | WD5003ABYX 500GB SATA HDD |
| Datastore Type | VMFS6                     |

Initial Situation

Additional storage was required to support:

- Windows Server 2019 VM
- Windows 10 IT Workstation VM
- Future infrastructure projects
- Snapshot storage
- ISO image storage

A dedicated 500GB Western Digital enterprise hard disk was installed in the ESXi host.

### Procedure

Increase capacity
→ Expand existing ESXi disk datastore
→ Use all remaining free space

Step 1 – Verify Disk Detection

Navigate to:

Host
→ Storage
→ Devices

The ESXi host successfully detected the new storage device:

WDC WD5003ABYX
Capacity: 465.76 GB
Status: Normal

Figure 1 – New 500GB disk detected by ESXi host.

(insert datastore.png)


## Skills Demonstrated

- VMware ESXi
- Virtualization
- Windows Server
- Active Directory
- Storage Management
- VM Administration

---
## Lessons Learned
