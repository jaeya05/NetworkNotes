---
description: >-
  This page described how to configure and troubleshoot the IP services in
  Paloalto firewall
---

# 🔐 Initial Configuration

### Configuration mode

To execute new configurations or edit the existing config's we've to first enter into configure mode

```basic
admin@PeerFound_Fw_01> configure
Entering configuration mode
[edit]
admin@PeerFound_Fw_01#

```

use "`exit`" keyword to get back to the cli mode

```basic
admin@PeerFound_Fw_01# exit
Exiting configuration mode
admin@PeerFound_Fw_01>
```

### Formatting Output

while working on cli we use to verify few configs by running show commands in cli, we can print the output from cli in different formats that are json, set, xml

```
admin@PeerFound_Fw_01> set cli config-output-format
  default   default
  json      json
  set       set
  xml       xml

```

#### SET Format&#x20;

Displays the output in configured format

```basic
admin@PeerFound_Fw_01> set cli config-output-format set
admin@PeerFound_Fw_01>
admin@PeerFound_Fw_01> configure
Entering configuration mode
[edit]
admin@PeerFound_Fw_01#
[edit]
admin@PeerFound_Fw_01# show deviceconfig system
set deviceconfig system type static
set deviceconfig system update-server updates.paloaltonetworks.com
set deviceconfig system update-schedule threats recurring weekly day-of-week wednesday
set deviceconfig system update-schedule threats recurring weekly at 01:02
set deviceconfig system update-schedule threats recurring weekly action download-only
set deviceconfig system timezone US/Pacific
set deviceconfig system service disable-telnet yes
set deviceconfig system service disable-http yes
set deviceconfig system hostname PeerFound_Fw_01
set deviceconfig system ip-address 192.168.137.129
set deviceconfig system netmask 255.255.255.0
set deviceconfig system default-gateway 192.168.137.2
set deviceconfig system dns-setting servers primary 1.1.1.1
set deviceconfig system dns-setting servers secondary 8.8.8.8
[edit]
admin@PeerFound_Fw_01#

```

#### json

Displays the output in json, which helps in dealing with API realted configs

```
admin@PeerFound_Fw_01# show deviceconfig system
{
"type":
{
"static":
[]
}
,
"update-server":
"updates.paloaltonetworks.com",
"update-schedule":
{
"threats":
{
"recurring":
{
"weekly":
{
"day-of-week":
"wednesday",
"at":
"01:02",
"action":
"download-only"}
}
}
}
,
"timezone":
"US/Pacific",
"service":
{
"disable-telnet":
"yes",
"disable-http":
"yes"}
,
"hostname":
"PeerFound_Fw_01",
"ip-address":
"192.168.137.129",
"netmask":
"255.255.255.0",
"default-gateway":
"192.168.137.2",
"dns-setting":
{
"servers":
{
"primary":
"1.1.1.1",
"secondary":
"8.8.8.8"}
}
}
[edit]
admin@PeerFound_Fw_01#

```

### Configuring Host name

```basic
admin@PA-VM# set deviceconfig system hostname PeerFound_Fw_01

[edit]
admin@PA-VM# commit

Commit job 5 is in progress. Use Ctrl+C to return to command prompt
...99%.......100%
Configuration committed successfully

[edit]
admin@PeerFound_Fw_01#

```

### Configuring Management IP address

#### Syntax

#### Static IP configuration

Syntax

```
admin@PeerFound_Fw_01# set deviceconfig system ip-address <ip address> netmask <netmask> default-gateway <default gateway> dns-setting servers primary <DNS ip address>
```

Setting management interface to type static

```basic
admin@PeerFound_Fw_01# set deviceconfig system type static
```

configuring the static IP address to the interface

```
admin@PeerFound_Fw_01# set deviceconfig system ip-address 192.168.137.129 netmask 255.255.255.0 default-gateway 192.168.137.254 dns-setting servers primary 1.1.1.1
```

_<mark style="color:red;">Note :</mark> <mark style="color:green;">we can execute the commands in single line as mentioned above whereas we can execute the commands one by one as mentioned below</mark>_

```
admin@PeerFound_Fw_01# set deviceconfig system ip-address 192.168.137.129 netmask 255.255.255.0
```

<pre><code><strong>admin@PeerFound_Fw_01# set deviceconfig system default-gateway 192.168.137.2</strong></code></pre>

```basic
admin@PeerFound_Fw_01# set deviceconfig system dns-setting servers primary 1.1.1.1 secondary 8.8.8.8
```



#### DHCP IP Configuration

#### Verifying the Management Interface

```basic
admin@PeerFound_Fw_01> show interface management


-------------------------------------------------------------------------------
Name: Management Interface
Link status:
  Runtime link speed/duplex/state: 1000/full/up
  Configured link speed/duplex/state: auto/auto/auto
MAC address:
  Port MAC address 50:ea:2f:00:01:00

Ip address: 192.168.137.129
Netmask: 255.255.255.0
Default gateway: 192.168.137.2
Ipv6 address: unknown
Ipv6 link local address: fe80::52ea:2fff:fe00:100/64
Ipv6 default gateway:
-------------------------------------------------------------------------------


-------------------------------------------------------------------------------
Logical interface counters:
-------------------------------------------------------------------------------
bytes received                    22686
bytes transmitted                 15526
packets received                  70
packets transmitted               87
receive errors                    0
transmit errors                   0
receive packets dropped           0
transmit packets dropped          0
multicast packets received        0
-------------------------------------------------------------------------------

```

_<mark style="color:red;">Note:</mark> <mark style="color:green;">we can execute the show commands from configuration mode itself, for the we need include</mark> <mark style="color:orange;">"</mark><mark style="color:orange;"><mark style="color:blue;">run<mark style="color:blue;"></mark><mark style="color:orange;">"</mark> <mark style="color:green;">keyword, beginning of the show commands as mentioned below.</mark>_

```
admin@PeerFound_Fw_01# run show interface management
```

