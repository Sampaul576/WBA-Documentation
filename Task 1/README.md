# Networking Task 01

This repository contains the work completed for Networking Task 01. The objective of this task was to understand basic networking concepts, inspect the network configuration of a Linux system, perform connectivity tests, and visualize how a device communicates with the internet.

---

## Project Files

```text
Networking_Task_01_Student/
│
├── README.md
├── Part_A_Network_Information.md
├── Part_B_Networking_Concepts.md
├── Part_D_Connectivity_Test.md
│
├── network_diagram/
│   └── network_diagram.svg
│
└── screenshots/
    └── command_outputs.md
```

### File Description

* **README.md** – Overview of the task and project contents.
* **Part_A_Network_Information.md** – Network details collected from the Linux system.
* **Part_B_Networking_Concepts.md** – Short explanations of important networking terms.
* **Part_D_Connectivity_Test.md** – Results of ping and traceroute tests.
* **network_diagram.svg** – Diagram showing the communication path from device to internet.
* **command_outputs.md** – Terminal outputs used during the task.

---

## Network Information Collected

The following details were identified from the system configuration:

| Parameter       | Value             |
| --------------- | ----------------- |
| Hostname        | vm                |
| IPv4 Address    | 192.0.2.2         |
| MAC Address     | 02:fc:00:00:00:05 |
| Default Gateway | 192.0.2.1         |
| DNS Server      | 8.8.8.8           |
| Interface       | eth0              |

---

## Concepts Covered

During this task, the following networking concepts were reviewed:

* IP Address and its purpose
* Difference between IPv4 and IPv6
* MAC Address
* DNS (Domain Name System)
* Default Gateway
* Private and Public IP Addresses
* LAN, MAN, and WAN
* Basic TCP/IP communication
* Common networking devices such as routers, switches, and access points

---

## Connectivity Testing

To verify network connectivity, ping and traceroute commands were used.

### Ping Test

* Destination: `google.com`
* Result: Successful
* Packet Loss: 0%
* Average Response Time: Approximately 3.25 ms

### Traceroute Test

* Total Hops: 6
* Purpose: To observe the path taken by packets from the local machine to the destination server.

The results indicate that the system was able to communicate with external servers without any packet loss or significant delay.

---

## Commands Used

```bash
hostname
cat /etc/resolv.conf
cat /proc/net/arp
cat /proc/net/fib_trie

ping -c 4 google.com
traceroute google.com
```

---
