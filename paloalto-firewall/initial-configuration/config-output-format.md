# Config Output Format

### Formatting Output

while working on cli we use to verify few configs by running show commands in cli, we can print the output from cli in different formats that are _<mark style="color:purple;">**json, set, xml.**</mark>_

```basic
admin@PeerFound_Fw_01> set cli config-output-format
  default   default
  json      json
  set       set
  xml       xml
```

#### SET Format

```
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
