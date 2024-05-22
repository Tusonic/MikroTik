## Mikrotik AP
```
/interface bridge add name=bridge1 protocol-mode=none
/interface wifi set [ find default-name=wifi1 ] channel.band=2ghz-g .frequency=2300-7300 .width=20mhz configuration.mode=ap .ssid=WIFISSID123 disabled=no security.authentication-types=wpa-psk,wpa2-psk .encryption="" .passphrase=haslo12345
/port set 0 name=serial0
/interface bridge port add bridge=bridge1 edge=yes interface=wifi1
/interface bridge port add bridge=bridge1 edge=yes interface=ether1
/interface bridge port add bridge=bridge1 edge=yes interface=ether2
/interface bridge port add bridge=bridge1 edge=yes interface=ether3
/interface bridge port add bridge=bridge1 edge=yes interface=ether4
/ip dhcp-client add interface=bridge1
/system identity set name=MT-AP
/system note set show-at-login=n
 ```


## (CISCO) edge=yes
```
/interface bridge port set bridge=bridge edge=yes 
 ```