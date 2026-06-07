Part A: Network Information
System Network Details
Field	Value
Hostname (Device Name)	vm
IPv4 Address	192.0.2.2
MAC Address	02:fc:00:00:00:05
Default Gateway	192.0.2.1
DNS Server	8.8.8.8 (Google Public DNS)
Network Interface	eth0
Subnet	192.0.2.0/24
How These Were Found (Linux Commands Used)
Hostname
$ hostname
vm
IP Address & MAC Address
$ cat /proc/net/arp
IP address       HW type     Flags       HW address            Mask     Device
192.0.2.1        0x1         0x2         02:fc:00:00:00:05     *        eth0
Device IP retrieved from /proc/net/fib_trie:
• Device IP: 192.0.2.2
• Gateway IP: 192.0.2.1
DNS Server
$ cat /etc/resolv.conf
nameserver 8.8.8.8
Note: Screenshots are included in the /screenshots folder.
