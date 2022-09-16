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

#### Set Format

Displays the configuration output in set format

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

#### Json Format

Displays the config output in json, this format helps while working with API realted configs

```json
admin@PeerFound_Fw_01> set cli config-output-format json
admin@PeerFound_Fw_01>
admin@PeerFound_Fw_01> configure
Entering configuration mode
[edit]
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

#### XML Format



```xml
admin@PeerFound_Fw_01> set cli config-output-format xml
admin@PeerFound_Fw_01>
admin@PeerFound_Fw_01> configure
Entering configuration mode
[edit]
admin@PeerFound_Fw_01# show deviceconfig system
<response status="success" code="19">
  <result total-count="1" count="1">
    <system>
      <type>
        <static/>
      </type>
      <update-server>updates.paloaltonetworks.com</update-server>
      <update-schedule>
        <threats>
          <recurring>
            <weekly>
              <day-of-week>wednesday</day-of-week>
              <at>01:02</at>
              <action>download-only</action>
            </weekly>
          </recurring>
        </threats>
      </update-schedule>
      <timezone>US/Pacific</timezone>
      <service>
        <disable-telnet>yes</disable-telnet>
        <disable-http>yes</disable-http>
      </service>
      <hostname>PeerFound_Fw_01</hostname>
      <ip-address>192.168.137.129</ip-address>
      <netmask>255.255.255.0</netmask>
      <default-gateway>192.168.137.2</default-gateway>
      <dns-setting>
        <servers>
          <primary>1.1.1.1</primary>
          <secondary>8.8.8.8</secondary>
        </servers>
      </dns-setting>
    </system>
  </result>
</response>
[edit]
admin@PeerFound_Fw_01#s
```
