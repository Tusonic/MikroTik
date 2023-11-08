## Dual Backup Wifi WAN
```:if ([/ip firewall address-list find list="backup"] != "")  do={
  /interface set [find name="ether1"] disabled=yes
  /interface set [find name="wifi1_WAN"] disabled=no
} else={
  /interface set [find name="ether1"] disabled=no 
  /interface set [find name="wifi1_WAN"] disabled=yes
}
```