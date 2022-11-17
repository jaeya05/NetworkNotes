---
description: This page consist Essential configration commands of the fortigate firewall
---

# Basic Configurations

#### <mark style="color:orange;">Hostname Config</mark>



```bash
FortiGate-VM64-KVM # config system global
FortiGate-VM64-KVM (global) # set hostname FW2
FortiGate-VM64-KVM (global) # end
FW2 # config
```

#### <mark style="color:orange;">Interface configuration</mark>

_**show system interface**_ will display the listed interface along with it's configuration as shown in the below mentioned **fig 1.1**

```bash
FortiGate-VM64-KVM # show system interface
```

<figure><img src="../../../.gitbook/assets/shosysteminterface.png" alt=""><figcaption><p>Fig 1.1</p></figcaption></figure>

```bash
FW01#config system interface
```

```bash
FW01(config)# edit port5
```
