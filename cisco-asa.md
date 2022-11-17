---
description: This page contains Cisco ASA Firewall troubleshoot
---

# Cisco ASA

### Verify the Access status of Packet flow

The packet-tracer command provides detailed information about the packets and how they are processed by the security appliance.

#### syntax

packet-tracer input _<mark style="color:green;">`<ZONE_NAME>`</mark>  <mark style="color:red;">\<protocol></mark>  <mark style="color:orange;">\<source-ip> \<source-port></mark>  <mark style="color:purple;">\<dest-ip> \<dst-port></mark>_ detailed

* _<mark style="color:orange;">\[src\_int]</mark>_: Specify the source (ingress) interface from which the simulated packet will start.
* _<mark style="color:red;">protocol</mark>_<mark style="color:red;">:</mark> This can be “**tcp**” or “**udp**” or “**icmp**“.
* _<mark style="color:orange;">src\_addr</mark>_<mark style="color:orange;">:</mark> Here enter a source IP address of the packet.
* _<mark style="color:orange;">src\_port</mark>_<mark style="color:orange;">:</mark> Source port of the packet (can be any arbitrary number, preferably above 1024).
* _<mark style="color:purple;">dest\_addr</mark>_<mark style="color:purple;">:</mark> Destination IP address of the packet.
* _<mark style="color:purple;">dest\_port</mark>_<mark style="color:purple;">:</mark> Destination port of the packet.
* _\[detailed]_: Provides detailed tracing output information.
* _\[xml]_: Displays the trace results in XML format.

#### Example Command

```powershell
ASA# packet-tracer input INSIDE tcp 10.18.19.20 1024 172.27.19.24 23 detailed
```

### :computer:Remote VPN Troubleshoot

#### verify the VPN overall status (VPN Summary)

```powershell
ASA# show vpn-sessiondb summary
```

Verify the user who connected to the firewall using <mark style="color:red;">**anyconnect**</mark> VPN

#### syntax

```powershell
ASAv# show vpn-sessiondb anyconnect filter a-ipaddress <ip-address>
```
