---
description: In this section Linux firewall configs and troubleshooting are documented
---

# Linux Firewall

### Configuring Linux Firewall

Linux Firewall helps us to permit or deny the network traffics which comes from Public (Internet) or distrust zone. the rules which we right on Linux firewalls are quit similar to Network ACL ( <mark style="color:red;">A</mark>ccess <mark style="color:red;">C</mark>ontrol <mark style="color:red;">L</mark>ist )

This commands will be executable on following Distros, RHEL / Centos / Oracle Linux

#### Permit the network traffic based on TCP/UDP port numbers

```bash
firewall-cmd --zone=public --add-port=80/tcp --permanent
```
