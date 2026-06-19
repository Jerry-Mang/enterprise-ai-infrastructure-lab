## Objectives

Deploy a multi-node wireless mesh network using Ruijie EW1200R routers and manage the deployment remotely through Ruijie Cloud.

The project was designed to simulate a small branch office wireless deployment where a root router provides network services and additional wireless repeaters extend Wi-Fi coverage to remote areas without Ethernet cabling.


### Technologies Used

Wireless Mesh
Router Mode
DHCP
NAT
Cloud Management
Web Tunnel
Remote Access
Wireless Backhaul

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

Wireless Mesh

Both additional EW1200R units were powered on and automatically joined the root router as repeaters.

Cloud status:

Synced
Online

No manual WDS configuration was required.

Client Testing

Successfully connected:

EZVIZ Wireless Camera

Assigned IP:

172.16.21.70

Verified:

Wireless association
DHCP assignment
Internet access
Mesh backhaul operation
Findings
Automatic LAN Conflict Detection

Attempted LAN configuration:

172.16.20.180

System automatically changed to:

172.16.21.180

Reason:

The WAN interface was already operating on:

172.16.20.0/24

Using the same subnet on both WAN and LAN would create routing conflicts.

ReyeeOS therefore automatically created:

LAN = 172.16.21.0/24

to maintain proper NAT functionality.

### Skills Demonstrated

Wireless Mesh Deployment
Wireless Repeater Configuration
DHCP Services
NAT
Layer 3 Routing Concepts
Wireless Client Provisioning
Cloud Management
Remote Monitoring
Network Troubleshooting
