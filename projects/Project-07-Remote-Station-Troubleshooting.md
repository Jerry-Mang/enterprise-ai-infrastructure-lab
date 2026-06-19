## Remote Station Trunk Deployment and Troubleshooting

### Overview

This project documents the deployment of a remote CCTV testing station connected to the main lab infrastructure through a Cisco Catalyst 3560 switch and a Ruijie/Reyee ES226 PoE switch.

The objective was to extend VLAN connectivity from the main rack to a secondary workstation used for CCTV, NVR and IP camera testing.

---

### Network Desgin

```text
Main Lab Rack

Cisco 1941 Router
        |
Cisco Catalyst 3560 (SW1)
        |
     Fa0/14
      Trunk
        |
Ruijie ES226 PoE Switch
        |
Remote CCTV Test Station
```

### VLAN Structure

| VLAN   | Purpose            | Subnet         |
| ------ | ------------------ | -------------- |
| VLAN10 | Staff Network      | 172.16.10.0/24 |
| VLAN20 | CCTV Network       | 172.16.20.0/24 |
| VLAN50 | Management Network | 172.16.50.0/24 |
| VLAN60 | Guest Network      | Reserved       |

---

### Objective
To provide a dedicated remote workstation capable of:

- IP Camera testing
- NVR commissioning
- PoE testing
- Network troubleshooting
- CCTV infrastructure validation

while maintaining VLAN separation across the lab.

---

### Cisco Switch Configuration:
SW1 Fa0/14

```text
interface FastEthernet0/14
description Uplink-to-Remote-Station
switchport trunk encapsulation dot1q
switchport trunk native vlan 50
switchport trunk allowed vlan 10,20,50,60
switchport mode trunk
spanning-tree portfast trunk
```

Verification:

```text
show interfaces trunk
show interfaces f0/14 switchport
```

Result:

```text
Status: trunking
Native VLAN: 50
Allowed VLANs: 10,20,50,60
```

---

### Problem Encountered

The remote station initially failed to connect.

Observed symptoms:

- ES226 intermittently offline
- Ruijie Cloud disconnected
- SW1 Fa0/18 reported notconnect
- SW1 Fa0/22 reported notconnect

---

### Troubleshooting Process
Step 1 – Layer 1 Verification

Tested physical connectivity using:

- Known-good patch leads
- Multiple switch ports
- Direct laptop connection

Results:

Fa0/18 -> No link
Fa0/22 -> No link

No link LEDs were present.

---

Step 2 – Alternative Port Testing

Additional ports were tested.

Fa0/13 -> Operational
Fa0/14 -> Operational

Fa0/14 successfully established a trunk connection.

---

Step 3 – Trunk Verification

Executed:

show interfaces trunk

Confirmed:

Fa0/14 trunking successfully

---

Step 4 – ES226 Recovery

The ES226 switch was restored and successfully connected to Ruijie Cloud.

Management information:

IP Address: 172.16.50.21
Gateway: 172.16.50.1
Cloud Status: Connected

---

Root Cause

The issue was traced to faulty or non-functional switch ports on the Cisco Catalyst 3560.

Affected ports:

Fa0/18
Fa0/22

These ports failed Layer 1 connectivity tests.

The trunk was moved to:

Fa0/14

which immediately restored service.

---

### Lessons Learned
Always verify Layer 1 first

Before investigating:

- VLAN configuration
- Routing
- DHCP
- Cloud connectivity

verify:

- Link LEDs
- Port status
- Physical cabling

---

### Use show commands

Useful Cisco commands:

```text
show interfaces status
show interfaces trunk
show interfaces switchport
show mac address-table
```

### Document findings
Maintaining documentation significantly reduces troubleshooting time and provides evidence of practical networking experience.

---

### Skills Demonstrated
- VLAN deployment
- 802.1Q trunking
- Cisco Catalyst administration
- Ruijie/Reyee switch management
- Physical layer troubleshooting
- Network fault isolation
- CCTV infrastructure support
- Structured troubleshooting methodology

---

Outcome: Successfully restored connectivity to the remote CCTV testing station and re-established cloud management connectivity for the ES226 PoE switch.

Outcome: Successfully restored connectivity to the remote CCTV testing station and re-established cloud management connectivity for the ES226 PoE switch.

