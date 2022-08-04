---
description: This page contains Cisco ASA Firewall troubleshoot
---

# Cisco ASA

### Remote VPN Troubleshoot

Verify the user by using assigned IP address from the VPN pool

```
ASAv-VPN/sec/act# show vpn-sessiondb anyconnect filter a-ipaddress  $

#Output
Session Type: AnyConnect

Username     : testuser              Index        : 2141
Assigned IP  : 172.16.16.10          Public IP    : 106.108.109.101
Protocol     : AnyConnect-Parent SSL-Tunnel DTLS-Tunnel
License      : AnyConnect Premium
Encryption   : AnyConnect-Parent: (1)none  SSL-Tunnel: (1)AES-GCM-256  DTLS-Tunnel: (1)AES-GCM-256
Hashing      : AnyConnect-Parent: (1)none  SSL-Tunnel: (1)SHA384  DTLS-Tunnel: (1)SHA384
Bytes Tx     : 240157846              Bytes Rx     : 122246482
Group Policy : TEST_VPN_POLICY      Tunnel Group : NEW_VPN
Login Time   : 09:57:11 EST Wed Aug 3 2022
Duration     : 23h:59m:32s
Inactivity   : 0h:00m:00s
VLAN Mapping : N/A                    VLAN         : none
Audt Sess ID : 0a7e1ffd0092700062ea7eb7
Security Grp : none                   

ASA-VPN/sec/act# 
```
