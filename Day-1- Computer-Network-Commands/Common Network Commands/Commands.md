```bash
1. ifconfig
```

```bash
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 192.168.174.133  netmask 255.255.255.0  broadcast 192.168.174.255
        inet6 fe80::20c:29ff:fee6:4d4a  prefixlen 64  scopeid 0x20<link>
        ether 00:0c:29:e6:4d:4a  txqueuelen 1000  (Ethernet)
        RX packets 1583  bytes 257680 (251.6 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 409  bytes 42985 (41.9 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 56  bytes 4816 (4.7 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 56  bytes 4816 (4.7 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0



```
---
```bash
2. ip a
```
<!-- new version of ifconfig -->
```bash
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000                                                                                  
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00                                 
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host 
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc pfifo_fast state UP group default qlen 1000
    link/ether 00:0c:29:e6:4d:4a brd ff:ff:ff:ff:ff:ff
    inet 192.168.174.133/24 brd 192.168.174.255 scope global dynamic noprefixroute eth0
       valid_lft 1762sec preferred_lft 1762sec
    inet6 fe80::20c:29ff:fee6:4d4a/64 scope link noprefixroute 
       valid_lft forever preferred_lft forever

```
---
```bash
iwconfig
```
```bash
lo        no wireless extensions.

eth0      no wireless extensions.

wlan0     IEEE 802.11  ESSID:off/any  
          Mode:Managed  Access Point: Not-Associated   Tx-Power=20 dBm   
          Retry short limit:7   RTS thr=2347 B   Fragment thr:off
          Encryption key:off
          Power Management:off
		  
```
---
```bash
arp -a
```

```bash
ip n
```

```bash
ping 192.168.15.1
```

```bash
netstat -ano
```

```bash 
route
```

```bash
ip r```
