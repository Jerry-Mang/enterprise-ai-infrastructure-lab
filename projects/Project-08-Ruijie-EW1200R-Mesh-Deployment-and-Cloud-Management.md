## Overview

This project documents the deployment and testing of a Ruijie EW1200R wireless mesh network environment.

The objective was to simulate a small branch office or remote site deployment where a root router provides Internet connectivity and additional wireless repeaters extend network coverage without requiring Ethernet cabling.

The deployment was fully managed through Ruijie Cloud and included remote device management, mesh synchronization, NAT services, DHCP services, client onboarding and wireless camera connectivity testing.

---

### Objectives

- Deploy a multi-node wireless mesh network using Ruijie EW1200R routers
- Validate automatic mesh pairing functionality
- Test wireless backhaul operation
- Verify DHCP and NAT services
- Test remote cloud management capabilities
- Validate Web Tunnel remote access functionality
- Connect and test wireless IP camera operation through the mesh network

---

### Technologies Used

- Ruijie ER1200R
- ReyeeOS
- Wireless Mesh Networking
- NAT
- DHCP
- Wireless Backhaul
- Ruijie Cloud
- Web Tunnel Remote Management
- Wireless Client Provisioning

---

### Equipment

| Device           | Model                           | 
| --------         | --------------------------------| 
| Root Router      | EW1200R                         | 
| Repeater 1       | EW1200R                         | 
| Repeater 2       | EW1200R                         |
| Access Switch    | RG-ES226GC-P (Existing Station) |
| Wireless Camera	 | EZVIZ Camera CS-CV310           | 

---

### Physical Topology

---

### Configuration

---

### Wireless Mesh

Both additional EW1200R units were powered on and automatically joined the root router as repeaters.

Cloud status:

Synced
Online

No manual WDS configuration was required.

---

### Client Testing

Successfully connected:

```text
EZVIZ Wireless Camera
```

Assigned IP:

```text
172.16.21.70
```

Verified:

- Wireless association
- DHCP assignment
- Internet access
- Mesh backhaul operation

---

### Findings

Automatic LAN Conflict Detection

Attempted LAN configuration:

```text
172.16.20.180
```

System automatically changed to:

```text
172.16.21.180
```

Reason:

The WAN interface was already operating on:

```text
172.16.20.0/24
```

Using the same subnet on both WAN and LAN would create routing conflicts.

ReyeeOS therefore automatically created:

```text
LAN = 172.16.21.0/24
```

to maintain proper NAT functionality.

---

### Key Features Tested

#### Root Router Deployment

WAN:

172.16.20.80

LAN:

172.16.21.180

#### Automatic Mesh Pairing

Using:

Mesh / Sync Button

to onboard additional EW1200R devices.

Wireless Backhaul

Root

↓

Repeater

↓

Repeater

No Ethernet cabling required.

#### Cloud Management

All devices synchronized successfully with Ruijie Cloud.

Web Tunnel Remote Access

Verified remote access to all mesh devices through Ruijie Cloud without port forwarding.

#### Client Connectivity

Successfully connected:

EZVIZ Wireless Camera

172.16.21.70

---

### Skills Demonstrated

- Wireless Mesh Deployment
- Wireless Repeater Configuration
- DHCP Services
- NAT
- Wireless Backhaul Technologies
- Layer 3 Routing Concepts
- Wireless Client Provisioning
- Cloud Management
- Remote Monitoring
- Remote Troubleshooting
- Network Validation
- Small Branch Network Deployment

---

### Lessons Learned

This project provided practical experience with enterprise-style wireless mesh deployments and demonstrated how Ruijie Cloud can simplfy remote network management.

The deployment also highlighted the importantce of Layer 3 design considerations, particularly WAN and LAN subnet separation when NAT services are enabled.

The sutomatic subnet conflict detection feature within ReyeeOS provided additional insight into how modern networking platforma protect administrators from common configuration mistakes.
