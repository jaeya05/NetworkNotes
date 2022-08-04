---
description: This page contains Cisco ASA Firewall troubleshoot
---

# Cisco ASA

### Verify the Access status of Packet flow

#### syntax

packet-tracer input _<mark style="color:green;">`<ZONE_NAME>`</mark> <mark style="color:red;">\<protocol></mark> <mark style="color:orange;">\<source-ip> \<source-port></mark> <mark style="color:purple;">\<dest-ip> \<dst-port></mark>_ detailed&#x20;

#### Example Command

```
ASA# packet-tracer input INSIDE tcp 10.18.19.20 1024 172.27.19.24 23 detailed
```

### Remote VPN Troubleshoot

Verify the user by using assigned IP address from the VPN pool

```shell
ASAv# show vpn-sessiondb anyconnect filter a-ipaddress <ip-address>
```
