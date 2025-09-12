# Lab – Calculate IPv4 Subnets

## Objectives

- **Part 1:** Determine IPv4 Address Subnetting  
- **Part 2:** Calculate IPv4 Address Subnetting

---

## Background / Scenario

Understanding how to calculate IPv4 subnet information is essential for network design and troubleshooting. This lab reinforces how to compute network IP address information from a given IP address and subnet mask.

---

## Required Resources

- 1 PC (Windows with Internet access)  
- Optional: IPv4 address calculator

---

## Instructions

Fill out the tables below with appropriate answers based on the given IP address, original subnet mask, and new subnet mask.

---

### Problem 1

**Given:**

- Host IP Address: `192.168.200.139`  
- Original Subnet Mask: `255.255.255.0`  
- New Subnet Mask: `255.255.255.224`

**Find:**

| Item                                      | Value |
|-------------------------------------------|-------|
| Number of Subnet Bits                     | 27-24= 3      |
| Number of Subnets Created                 | 2^3= 8      |
| Number of Host Bits per Subnet            | 32-27= 5      |
| Number of Hosts per Subnet                | 2^5-2= 30      |
| Network Address of this Subnet            | 192.168.200.128      |
| IPv4 Address of First Host on this Subnet | 192.168.200.127      |
| IPv4 Address of Last Host on this Subnet  | 192.168.200.158      |
| IPv4 Broadcast Address on this Subnet     | 192.168.200.159      |

---

### Problem 2

**Given:**

- Host IP Address: `10.101.99.228`  
- Original Subnet Mask: `255.0.0.0`  
- New Subnet Mask: `255.255.128.0`

**Find:**

| Item                                      | Value |
|-------------------------------------------|-------|
| Number of Subnet Bits                     | 17-8= 9      |
| Number of Subnets Created                 | 2^9= 512      |
| Number of Host Bits per Subnet            | 32-17= 15      |
| Number of Hosts per Subnet                | 2^15-2= 32,766      |
| Network Address of this Subnet            | 10.101.0.0      |
| IPv4 Address of First Host on this Subnet | 10.101.0.1      |
| IPv4 Address of Last Host on this Subnet  | 10.101.127.254      |
| IPv4 Broadcast Address on this Subnet     | 10.101.127.255      |

---

### Problem 3

**Given:**

- Host IP Address: `172.22.32.12`  
- Original Subnet Mask: `255.255.0.0`  
- New Subnet Mask: `255.255.224.0`

**Find:**

| Item                                      | Value |
|-------------------------------------------|-------|
| Number of Subnet Bits                     | 19-16= 3      |
| Number of Subnets Created                 | 2^3= 8      |
| Number of Host Bits per Subnet            | 32-19= 13      |
| Number of Hosts per Subnet                | 2^13-2= 8,190      |
| Network Address of this Subnet            | 172.22.32.0      |
| IPv4 Address of First Host on this Subnet | 172.22.32.1      |
| IPv4 Address of Last Host on this Subnet  | 172.22.63.254      |
| IPv4 Broadcast Address on this Subnet     | 172.22.63.255      |

---

### Problem 4

**Given:**

- Host IP Address: `192.168.1.245`  
- Original Subnet Mask: `255.255.255.0`  
- New Subnet Mask: `255.255.255.252`

**Find:**

| Item                                      | Value |
|-------------------------------------------|-------|
| Number of Subnet Bits                     | 30-24= 6      |
| Number of Subnets Created                 | 2^6= 64      |
| Number of Host Bits per Subnet            | 32-30= 2      |
| Number of Hosts per Subnet                | 2^2-2= 2      |
| Network Address of this Subnet            | 192.168.1.244      |
| IPv4 Address of First Host on this Subnet | 192.168.1.245      |
| IPv4 Address of Last Host on this Subnet  | 192.168.1.246      |
| IPv4 Broadcast Address on this Subnet     | 192.168.1.247      |

---

### Problem 5

**Given:**

- Host IP Address: `128.107.0.55`  
- Original Subnet Mask: `255.255.0.0` 
- New Subnet Mask: `255.255.255.0`

**Find:**

| Item                                      | Value |
|-------------------------------------------|-------|
| Number of Subnet Bits                     | 24-16= 8      |
| Number of Subnets Created                 | 2^8= 256      |
| Number of Host Bits per Subnet            | 32-24= 8      |
| Number of Hosts per Subnet                | 2^8-2= 254      |
| Network Address of this Subnet            | 128.107.0.0      |
| IPv4 Address of First Host on this Subnet | 128.107.0.1      |
| IPv4 Address of Last Host on this Subnet  | 128.107.0.254      |
| IPv4 Broadcast Address on this Subnet     | 128.107.0.255      |

---

### Problem 6

**Given:**

- Host IP Address: `192.135.250.180`  
- Original Subnet Mask: `255.255.255.0`  
- New Subnet Mask: `255.255.255.248`

**Find:**

| Item                                      | Value |
|-------------------------------------------|-------|
| Number of Subnet Bits                     | 29-24= 5      |
| Number of Subnets Created                 | 2^5= 32      |
| Number of Host Bits per Subnet            | 32-29= 3      |
| Number of Hosts per Subnet                | 2^3-2= 6      |
| Network Address of this Subnet            | 192.135.250.176      |
| IPv4 Address of First Host on this Subnet | 192.135.250.177      |
| IPv4 Address of Last Host on this Subnet  | 192.135.250.182      |
| IPv4 Broadcast Address on this Subnet     | 192.135.250.183      |

---

## Reflection Question

**Why is the subnet mask so important when analyzing an IPv4 address?**  
_Answer:_  
Knowing the subnet mask tells us the size of the network for efficiant data routing. It separates the network and host portions of the address, this helps determine if the destination is on the local network or if it needs to be rerouted.