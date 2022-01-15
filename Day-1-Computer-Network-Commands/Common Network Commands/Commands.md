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
3. iwconfig
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
4. arp -a
```

```bash
? (192.168.174.2) at 00:50:56:fb:38:47 [ether] on eth0
? (192.168.174.254) at 00:50:56:e6:25:e6 [ether] on eth0
? (192.168.174.129) at <incomplete> on eth0
```
---

```bash
5. ip n
```
```bash
192.168.174.2 dev eth0 lladdr 00:50:56:fb:38:47 STALE
192.168.174.254 dev eth0 lladdr 00:50:56:e6:25:e6 STALE
192.168.174.129 dev eth0  FAILED
```
---
```bash
6. ping 192.168.15.1
```
```bash
PING google.com (142.250.206.110) 56(84) bytes of data.
64 bytes from del11s20-in-f14.1e100.net (142.250.206.110): icmp_seq=1 ttl=128 time=122 ms
64 bytes from del11s20-in-f14.1e100.net (142.250.206.110): icmp_seq=2 ttl=128 time=55.1 ms
64 bytes from del11s20-in-f14.1e100.net (142.250.206.110): icmp_seq=3 ttl=128 time=53.6 ms
^C
--- google.com ping statistics ---
3 packets transmitted, 3 received, 0% packet loss, time 2004ms
rtt min/avg/max/mdev = 53.632/76.982/122.225/31.996 ms
```
---

```bash
7. netstat -ano
```
```bash
Active Internet connections (servers and established)
Proto Recv-Q Send-Q Local Address           Foreign Address         State       Timer
udp        0      0 192.168.174.133:68      192.168.174.254:67      ESTABLISHED off (0.00/0/0)
raw6       0      0 :::58                   :::*                    7           off (0.00/0/0)
Active UNIX domain sockets (servers and established)
Proto RefCnt Flags       Type       State         I-Node   Path
unix  2      [ ACC ]     STREAM     LISTENING     19776    /run/uuidd/request
unix  2      [ ACC ]     STREAM     LISTENING     20168    /tmp/dbus
```
---

```bash 
8. route
```

```bash
Kernel IP routing table
Destination     Gateway         Genmask         Flags Metric Ref    Use Iface
default         192.168.174.2   0.0.0.0         UG    100    0        0 eth0
192.168.174.0   0.0.0.0         255.255.255.0   U     100    0        0 eth0
```
---
```bash
9. ip r
```
```bash
default via 192.168.174.2 dev eth0 proto dhcp metric 100 
192.168.174.0/24 dev eth0 proto kernel scope link src 192.168.174.133 metric 100 
```


