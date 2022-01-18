```bash
1. ifconfig
```
for checking ip address of a machine
![](images/ifconfig.png)


```
```bash
2. ip a
```
new version of ifconfig
![](images/ip-a.png)

---
```bash
3. iwconfig
```
For checking wireless network(wifi) ip

If You are on a virtual machine and wifi adaptor is not connected
then it will not show anything
![](images/iwconfig.png)

---
```
```bash
4. arp -a
```
Will show you every devices along with mac addresses those are connected to your network/device
![](images/arp.png)

---
```bash
5. ip n
```
new version of arp
![](images/ip-n.png)

---
```bash
6. ping 192.168.15.1
```
Ping is used to check is that host/ip is working or not 
(connectable or not)

![[ping.png]]

---
```bash
7. netstat -ano
```
What's open here, machine is talking with someone else, some like arp
![](images/netstat.png)

---
```bash 
8. route
```
Where your traffic exits essential
![](images/route.png)

---
```bash
9. ip r
```
new version of route
![](ip-r.png)