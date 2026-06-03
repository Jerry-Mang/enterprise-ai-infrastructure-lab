This project documents the deployment of a remote CCTV testing station using a Ruijie ES226 PoE switch connected to a Cisco Catalyst 3560 trunk port.

The objective was to extend the existing VLAN20 CCTV testing environment to a secondary workstation while maintaining management access through VLAN50.

### Network Topology

Cisco 3560 SW1
Fa0/14 (Trunk)
     |
     |
ES226 Port24 (Trunk)
     |
+----+----+
|         |
Port1     Port7
IPC       IPC
(VLAN20)  (VLAN20)

### Initial Problem

After configuring ports 1-10 as VLAN20 access ports:

- IPCs powered up correctly
- Link status showed 100M Full Duplex
- Devices did not appear in SADP
- No DHCP address was obtained

### Investigation

Port1 Connected

![Network Topology](../images/ES226_port1.png)

Figure 1 - IPC connected successfully to ES226 Port1.


Access VLAN1


Figure 2 - Uplink port configured as Access VLAN1.

### Findings:

The Cisco uplink was configured as an 802.1Q trunk while the ES226 uplink remained configured as an access port.

This prevented VLAN20 traffic from traversing the uplink.

### Root Cause

Root Cause:

ES226 Port24 was configured as:

Access VLAN1

while Cisco SW1 Fa0/14 was configured as:

Trunk
Allowed VLANs 10,20,50,60

As a result, VLAN20 traffic from IPC devices could not reach the CCTV network.

### Resolution

Actions performed:

1. Created VLAN20 (CCTV)
2. Created VLAN50 (Management)
3. Changed ES226 Port24 from Access to Trunk
4. Allowed VLANs 1,20,50
5. Verified cloud connectivity remained operational

Port24
Trunk
Allowed VLAN 1,20,50
Valid VLAN 1,20,50

Figure 4 - Final trunk configuration.

### Verification

Verification completed:

- IPC devices appeared in SADP
- VLAN20 connectivity restored
- Cloud management remained online
- Management IP 172.16.50.21 remained reachable

### Skills Demonstrated

Skills Demonstrated

- VLAN configuration
- 802.1Q trunking
- Layer 2 switching
- CCTV network deployment
- Network troubleshooting
- Root cause analysis
- Ruijie cloud management
- Cisco Catalyst switching


