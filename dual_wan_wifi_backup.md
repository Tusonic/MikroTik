## Dual Backup Wifi WAN
```
:if ([/ip firewall address-list find list="backup"] != "")  do={
  /interface set [find name="ether1"] disabled=yes
  /interface set [find name="wifi1_WAN"] disabled=no
} else={
  /interface set [find name="ether1"] disabled=no 
  /interface set [find name="wifi1_WAN"] disabled=yes
}
```

```
:if ([/ping 8.8.8.8 count=3] = 0) do={
  /ip firewall address-list add list=backup address=8.8.8.8 timeout=1h
} else={
  :log info "Ping 8.8.8.8 ok"
}
```