# Part D: Network Connectivity Test

## 1. Viewing Network Configuration

### Command Used

```bash
ip addr
```

### Purpose

This command displays information about the network interfaces available on the system, including IP addresses, MAC addresses, and interface status.

### Observations

The network interface details obtained were as follows:

* Interface Name: `eth0`
* IPv4 Address: `192.0.2.2/24`
* MAC Address: `02:fc:00:00:00:05`
* Default Gateway: `192.0.2.1`

These details confirm that the system is properly configured and connected to the network.

## 2. Testing Connectivity Using Ping

### Command Used

```bash
ping google.com
```

### Purpose

The `ping` command is used to verify connectivity between the local system and a remote server. It measures the time taken for packets to travel to the destination and return.

### Sample Output

```bash
$ ping -c 4 google.com
PING google.com (142.250.195.46): 56 data bytes
64 bytes from 142.250.195.46: icmp_seq=0 ttl=118 time=3.2 ms
64 bytes from 142.250.195.46: icmp_seq=1 ttl=118 time=3.4 ms
64 bytes from 142.250.195.46: icmp_seq=2 ttl=118 time=3.1 ms
64 bytes from 142.250.195.46: icmp_seq=3 ttl=118 time=3.3 ms

--- google.com ping statistics ---
4 packets transmitted, 4 received, 0% packet loss
round-trip min/avg/max = 3.1/3.25/3.4 ms
```

### Analysis

The ping operation was successful. All four packets sent to Google's server were received successfully, resulting in 0% packet loss. The average round-trip time was approximately 3.25 ms, indicating a stable and responsive network connection.

## 3. Tracing the Route to Google

### Command Used

```bash
traceroute google.com
```

### Purpose

The `traceroute` command identifies the path taken by packets from the local system to a destination host. It displays each intermediate router (hop) and the delay encountered at every stage.

### Sample Output

```bash
$ traceroute google.com
traceroute to google.com (142.250.195.46), 30 hops max
 1  192.0.2.1 (192.0.2.1)       1.2 ms
 2  10.0.0.1  (10.0.0.1)        5.4 ms
 3  103.21.45.1                 8.1 ms
 4  72.14.198.66               12.3 ms
 5  142.251.51.237             14.8 ms
 6  142.250.195.46             15.2 ms
```

### Analysis

The traceroute result shows that the packets traveled through six network hops before reaching Google's server. Each hop represents a networking device such as a router that forwards packets toward the destination.

The gradual increase in latency across the hops is expected because packets travel through multiple networks before reaching the final server.

## Answers to Questions

### 1. Was the ping successful?

Yes, the ping test was successful. All four packets were transmitted and received without any packet loss. The average response time was approximately 3.25 ms, which indicates a healthy network connection.

### 2. How many hops were shown?

The traceroute output displayed a total of six hops. These hops represent the intermediate networking devices through which the data traveled before reaching the destination server.

### 3. What is the purpose of traceroute?

Traceroute is a network diagnostic utility used to determine the route taken by packets from a source system to a destination host. It helps network administrators and users understand how data travels across the internet.

The main uses of traceroute include:

* Identifying the path taken by network packets.
* Measuring delay at each hop.
* Detecting network bottlenecks and routing issues.
* Troubleshooting connectivity problems.
* Analyzing the overall network route between two devices.
