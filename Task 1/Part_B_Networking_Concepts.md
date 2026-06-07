Part B: Basic Networking Concepts
What is an IP Address?
An IP (Internet Protocol) Address is a unique numerical label assigned to every device connected to a network. It functions much like a home address, helping data packets reach the correct destination.

• IPv4 Format Example: 192.168.1.5
• Consists of four numbers separated by dots, each ranging from 0–255.
• Every device on a network must have a unique IP address for proper communication.
What is a MAC Address?
A MAC (Media Access Control) Address is a hardware-level identifier assigned to a Network Interface Card (NIC) by the manufacturer. Unlike an IP address, it generally remains unchanged.

• Format Example: 02:fc:00:00:00:05
• Consists of six pairs of hexadecimal digits.
• Operates at the Data Link Layer (Layer 2) of the OSI Model.
• Used for communication within a local network.
What is a Default Gateway?
A Default Gateway is the networking device, usually a router, that forwards traffic from a local network to other networks such as the internet.

• Acts as the exit point from a local network.
• Example Gateway Address: 192.0.2.1
• All traffic destined for external networks is sent to the gateway first.
What is DNS?
DNS (Domain Name System) translates human-readable domain names into IP addresses.

• Example: google.com → corresponding IP address.
• Eliminates the need to remember numerical IP addresses.
• DNS Server Used: 8.8.8.8 (Google Public DNS).
Difference Between Public IP and Private IP
Feature	Private IP	Public IP
Scope	Used inside a local network	Used globally on the internet
Assigned by	Router (DHCP)	Internet Service Provider (ISP)
Uniqueness	Unique within local network	Globally unique
Visibility	Not visible on the internet	Visible to external servers
Example	192.168.x.x, 10.x.x.x, 172.16.x.x	103.21.45.200
Cost	Free	Managed/assigned by ISP

In simple terms, a device uses a private IP address within a local network, while the router uses a public IP address to communicate with the internet. This process is enabled through NAT (Network Address Translation).
