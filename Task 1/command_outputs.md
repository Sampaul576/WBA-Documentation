Command Outputs Log
(Text-based record of the commands executed and their outputs. Used in place of screenshots where direct image capture was not available.)
1. Checking the Hostname
Command:
hostname

Output:
vm

Observation:
The hostname of the virtual machine is vm.
2. Viewing the DNS Configuration
Command:
cat /etc/resolv.conf

Output:
nameserver 8.8.8.8

Observation:
The system is configured to use Google Public DNS (8.8.8.8) for domain name resolution.
3. Inspecting the ARP Table
Command:
cat /proc/net/arp

Output:
IP address       HW type     Flags       HW address            Mask     Device
192.0.2.1        0x1         0x2         02:fc:00:00:00:05     *        eth0

Observation:
Gateway IP Address: 192.0.2.1
MAC Address: 02:fc:00:00:00:05
Network Interface: eth0
4. Identifying the Device IP Address
Observation:
From the routing information, the local IP address assigned to the device is 192.0.2.2.
5. Testing Connectivity with Google
Observation:
All four packets were transmitted and received successfully with 0% packet loss, indicating stable connectivity.
6. Tracing the Route to Google
Observation:
The traceroute output shows the path taken by packets from the local machine to Google's server.
Conclusion
The network configuration was successfully examined using Linux networking files and commands. The hostname, DNS server, gateway information, MAC address mapping, local IP address, connectivity status, and route to an external server were identified and verified.
