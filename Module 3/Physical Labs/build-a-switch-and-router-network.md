# Lab - Use Ping and Traceroute to Test Network Connectivity
Aida Ochoa

## Topology & Addressing Table

| Device | Interface     | IP Address / Prefix         | Default Gateway     |
|--------|---------------|-----------------------------|---------------------|
| R1     | G0/0/0        | 64.100.0.2 /30              | N/A                 |
|        |               | 2001:db8:acad::2 /64        |                     |
|        |               | fe80::2                     |                     |
| R1     | G0/0/1        | 192.168.1.1 /24             | N/A                 |
|        |               | 2001:db8:acad:1::1 /64      |                     |
|        |               | fe80::1                     |                     |
| ISP    | G0/0/0        | 64.100.0.1 /30              | N/A                 |
|        |               | 2001:db8:acad::1 /64        |                     |
|        |               | fe80::1                     |                     |
| ISP    | G0/0/1        | 209.165.200.225 /27         | N/A                 |
|        |               | 2001:db8:acad:200::225 /64  |                     |
|        |               | fe80::225                   |                     |
| S1     | VLAN 1        | 192.168.1.2 /24             | 192.168.1.1         |
|        |               | 2001:db8:acad:1::2 /64      | fe80::1             |
|        |               | fe80::10                    |                     |
| PC-A   | NIC           | 192.168.1.10 /24            | 192.168.1.1         |
|        |               | 2001:db8:acad:1::10 /64     | fe80::1             |
| External | NIC         | 209.165.200.226 /27         | 209.165.200.225     |
|        |               | 2001:db8:acad:200::226 /64  | fe80::225           |

---

## Objectives

- **Part 1:** Build and Configure the Network  
- **Part 2:** Use Ping Command for Basic Network Testing  
- **Part 3:** Use Tracert and Traceroute Commands for Basic Network Testing  
- **Part 4:** Troubleshoot the Topology

---

## Required Resources

- 2 Routers (Cisco 4221 or comparable)  
- 1 Switch (Cisco 2960 or comparable)  
- 2 PCs  
- Console cables  
- Ethernet and serial cables  
- Terminal emulation software

---

## Part 1: Build and Configure the Network

### Step 1: Cable the network as shown in the topology

**Screenshot Placeholder:**  
`!Network Topology`

---

### Step 2: Erase configurations and reload devices

---

### Step 3: Configure PC IP addresses and default gateways

---

### Step 4: Configure R1, ISP, and S1 using provided initial configurations

**Screenshot Placeholder:**  
![alt text](image-4.png) 
![alt text](image-5.png)
![alt text](image-6.png)

---

### Step 5: Configure IP host table on R1

**Screenshot Placeholder:**  
![alt text](image-7.png)

---

## Part 2: Use Ping Command for Basic Network Testing

### Step 1: Test connectivity from PC-A

- **Ping default gateway (IPv4 and IPv6)**  
- **Record average round trip time and TTL/Hop Limit**

| Destination                  | Avg RTT (ms) | TTL / Hop Limit |
|-----------------------------|--------------|-----------------|
| 192.168.1.10                |              |                 |
| 2001:db8:acad:1::10         |              |                 |
| 192.168.1.1 (R1)            |              |                 |
| 2001:db8:acad:1::1 (R1)     |              |                 |
| 192.168.1.2 (S1)            |              |                 |
| 2001:db8:acad:1::2 (S1)     |              |                 |
| 64.100.0.2 (R1)             |              |                 |
| 2001:db8:acad::2 (R1)       |              |                 |
| 64.100.0.1 (ISP)            |              |                 |
| 2001:db8:acad::1 (ISP)      |              |                 |
| 209.165.200.225 (ISP G0/0/1)|              |                 |
| 2001:db8:acad:200::225      |              |                 |
| 209.165.200.226 (External)  |              |                 |
| 2001:db8:acad:200::226      |              |                 |

---

### Step 2: Use extended ping options on PC-A

- **Ping with `-t` option**  
- **Simulate link failure and observe ICMP error messages**  
- **Reconnect and verify recovery**

---

### Step 3: Test connectivity using Cisco devices

- **Ping External from R1 and S1**  
- **Use hostnames from IP host table**  
- **Use extended ping options and simulate failure**

---

## Part 3: Use Tracert and Traceroute Commands

### Step 1: Use `tracert` from PC-A to External

---

### Step 2: Explore `tracert` options (`-d`, etc.)

---

### Step 3: Use `traceroute` from R1 to External

---

### Step 4: Use `traceroute` from S1 to External
---

## Part 4: Troubleshoot the Topology

### Step 1: Apply incorrect configuration to ISP

---

### Step 2: Use ping and traceroute to identify and correct issues

- **Ping each hop**  
- **Use `show run` and `show ip interface brief`**  
- **Correct IP and IPv6 address issues**

---

## Reflection Questions

1. What could prevent ping or traceroute responses besides connectivity issues?  
   _Answer:_  Firewalls and security settings can block a ping or tracert command by blocking the traffic and not allowing it to actually connect. Also, if a network is using a VPN, that traffic can get lost or blocked.

2. What does the ping response to a non-existent address like 209.165.200.227 indicate?  
   _Answer:_  Request timed out and was 100% loss

3. What does the ping response to an unreachable network like 192.168.5.3 indicate?  
   _Answer:_  I received the same response, the request had timed out. SOmetimes it can say the destination host is unreachable.

4. What is the default IPv4 TTL on Windows and Cisco devices?  
   _Answer:_  For Windows devices it is 128, for Cisco it's 255.

5. What is the default IPv6 Hop Limit on Windows and Cisco devices?  
   _Answer:_  128 hops on Windows devices and 64 on CIsco devices.
