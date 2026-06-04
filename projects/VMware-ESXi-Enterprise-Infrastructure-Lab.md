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

![ New 500GB](../images/datastore.png)
Figure 1 – New 500GB disk detected by ESXi host.

Step 2 - Create New Database
Navigate to:

Storage
→ New Datastore

Select:

Create VMFS Datastore

Choose the newly installed 500GB disk.

Step 3 – Configure VMFS Datastore

Configure:

Datastore Name: test
Filesystem: VMFS6
Capacity: 465.76 GB

ESXi displayed the final datastore layout before creation.

![ New finish](../images/finish.png)
Figure 2 – VMFS datastore creation summary.

Step 4 – Expand Datastore Capacity

The datastore was later expanded using:

Storage
→ Increase Capacity
→ Expand an Existing VMFS Datastore Extent

This allowed the datastore to utilise the full available disk capacity.

![ New finish scuess](../images/finish_scuess.png)
Figure 3 – VMFS datastore expansion wizard.

Results

Successfully provisioned:

VMFS6 Datastore
Capacity: 465.76 GB

The datastore became available for:

Virtual machine storage
VM snapshots
ISO repositories
Future infrastructure projects
Skills Demonstrated
VMware ESXi Administration
Datastore Management
VMFS6 Filesystems
Storage Provisioning
Capacity Planning
Infrastructure Expansion
Virtualization Administration

---

Lessons Learned

This exercise provided practical experience with enterprise virtualization storage management, including:

Physical disk detection
Datastore creation
VMFS filesystem management
Storage capacity expansion
Resource planning for virtual infrastructure

---

