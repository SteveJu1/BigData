---

---

create vmware

NAT

partition: boot swap缓存 root

vi  /etc/sysconfig/network-scripts/ifcfg-eth0

```c#
DEVICE=eth0
TYPE=Ethernet
ONBOOT=yes
NM_CONTROLLED=yes
BOOTPROTO=static
IPADDR=
NETMASK=java
GATEWAY=
DNS1=144.144.144.144
DNS2=gateway
```

```bash
rm etc/udev(device)/rules.d/70-net
service network restart
```

network:change name



```bash
export PATH=$PATH:
source ~/.bashrc /etc/.bashrc
```

