# Secure Remote Infrastructure Access Lab using Tailscale VPN

## Overview

This project documents a secure remote access setup for my home enterprise-style IT lab using Tailscale VPN.

The lab allows remote administration of network, server, virtualisation, and CCTV infrastructure without exposing services directly to the public internet.

## Objective

The objective of this lab is to simulate a small enterprise environment where infrastructure can be securely managed remotely.

The setup is designed to practise real-world IT support, networking, infrastructure administration, and troubleshooting skills.

## Technologies Used

- Cisco 1941 Router
- Cisco Catalyst Switch
- VMware ESXi
- Windows Server 2019
- Windows 10 Client
- Active Directory Domain Services
- DNS and DHCP
- Tailscale VPN
- Hikvision NVR / CCTV infrastructure
- SSH, RDP, and Web GUI administration

## Lab Components

| Component | Purpose |
|---|---|
| Cisco Router | Inter-VLAN routing and gateway |
| Cisco Switch | VLAN access and trunking |
| ESXi Host | Virtual machine hosting |
| Windows Server 2019 | Domain Controller, DNS, DHCP |
| Windows 10 Client | Domain-joined test client |
| NVR / CCTV | Security infrastructure testing |
| Tailscale | Secure remote VPN access |

## Remote Access Design

Remote access is provided through Tailscale VPN.

This allows management access to internal lab devices such as:

- Cisco router and switch via SSH
- ESXi host via web interface
- Windows Server via RDP
- Windows 10 client via RDP
- NVR via web interface

No public port forwarding is required.

## Example Management IP Plan

| Device | IP Address | Access Method |
|---|---|---|
| R1 Router | 172.16.10.1 | SSH |
| SW1 Switch | 172.16.10.2 | SSH |
| Windows Server 2019 | 172.16.10.10 | RDP |
| Windows 10 Client | 172.16.10.11 | RDP |
| ESXi Host | 172.16.10.200 | Web GUI |
| NVR | 172.16.20.x | Web GUI |

## Key Skills Practised

- Secure remote infrastructure access
- VLAN-based network segmentation
- Cisco SSH management
- VMware ESXi administration
- Windows Server Active Directory administration
- Domain-joined Windows client testing
- CCTV/NVR network access
- Troubleshooting remote connectivity issues
- Technical documentation and SOP writing

## Troubleshooting Examples

Examples of issues investigated in this lab include:

- ESXi management access issues caused by incorrect VLAN tagging
- VM network connectivity problems
- Snapshot-related datastore space issues
- SSH access to incorrect management IP addresses
- Domain login verification using Active Directory credentials

## Security Considerations

- Management services are not exposed directly to the internet
- Remote access is performed through Tailscale VPN
- Infrastructure devices are accessed using private IP addresses
- Administrative access is limited to trusted devices
- VLANs are used to separate management, server, and CCTV traffic

## Outcome

This lab demonstrates the ability to securely access and manage a multi-device infrastructure environment remotely.

It provides practical experience in networking, virtualisation, Windows Server administration, remote access, and infrastructure troubleshooting.
