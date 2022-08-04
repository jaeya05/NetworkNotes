---
description: This page contains Cisco network product troubleshooting commands and notes
---

# General Troubleshoot

### Network Product Troubleshoot

#### Verify the Power Supply status

```
#Display the primary switch power supply unit status 
CISCO_SW_01#show env power
SW  PID                 Serial#     Status           Sys Pwr  PoE Pwr  Watts
--  ------------------  ----------  ---------------  -------  -------  -----
 1  Built-in                                         Good

#Display all the switches in stacks power supply status 
CISCO_SW_01#show env power all
SW  PID                 Serial#     Status           Sys Pwr  PoE Pwr  Watts
--  ------------------  ----------  ---------------  -------  -------  -----
 1  Built-in                                         Good
 2  Built-in                                         Good
 3  Built-in                                         Good
 4  Built-in                                         Good
```
