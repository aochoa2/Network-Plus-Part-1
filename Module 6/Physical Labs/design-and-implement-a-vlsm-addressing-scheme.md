# Lab – Design and Implement a VLSM Addressing Scheme

## Objectives

- **Part 1:** Examine Network Requirements  
- **Part 2:** Design the VLSM Address Scheme  
- **Part 3:** Cable and Configure the IPv4 Network

---

## Background / Scenario

Variable Length Subnet Masking (VLSM) allows subnetting a network multiple times to create subnets of various sizes based on host requirements. In this lab, you will use the `192.168.33.128/25` network to design a VLSM scheme for the topology. You will configure router interfaces and allocate addresses for future LANs.

---

## Required Resources

- 2 Routers (Cisco 4221 or comparable)  
- 2 Switches (Cisco 2960 or comparable)  
- 1 PC  
- Console cables  
- Ethernet and serial cables  
- Windows Calculator (optional)

---

## Part 1: Examine Network Requirements

### Step 1: Determine Available Hosts and Subnets

- How many host addresses are available in a /25 network?  
  _Answer:_  126 hosts
- What is the total number of host addresses needed in the topology?  
  _Answer:_  80
- How many subnets are needed in the network topology?  
  _Answer:_  6

---

### Step 2: Determine the Largest Subnet

- Subnet description:  
  _Answer:_  BR1 LAN
- Number of IP addresses required:  
  _Answer:_  40
- Subnet mask needed:  
  _Answer:_  255.255.255.192 OR /26
- Total host addresses supported:  
  _Answer:_  62
- Can the `/25` network support this subnet?  
  _Answer:_  yes
- Resulting network addresses:  
  _Answer:_  192.168.33.128 /26   192.168.33.192 /26
- Use the first network address for this subnet.
    192.168.33.128/26
---

### Step 3: Determine the Second Largest Subnet

- Subnet description:  
  _Answer:_  BR2 LAN
- Number of IP addresses required:  
  _Answer:_  25
- Subnet mask needed:  
  _Answer:_  255.255.255.224 OR /27
- Total host addresses supported:  
  _Answer:_  30 hosts
- Can the remaining subnet support this?  
  _Answer:_  YES
- Resulting network addresses:  
  _Answer:_  192.168.33.192 /27   192.168.33.224 /27
- Use the first network address for this subnet.
    192.168.33.192 /27
---

### Step 4: Determine the Third Largest Subnet

- Subnet description:  
  _Answer:_  BR2 loT LAN
- Number of IP addresses required:  
  _Answer:_  7
- Subnet mask needed:  
  _Answer:_  255.255.255.248 OR /29
- Total host addresses supported:  
  _Answer:_  6
- Can the remaining subnet support this?  
  _Answer:_  YES
- Resulting network addresses:  
  _Answer:_  192.168.33.224/29  192.168.33.232/29   192.168.33.240/29   192.168.33.248/29
- Use the first address for this subnet  - 192.168.33.224/29
- Use second for CCTV LAN  - 192.168.33.232/29
- Use third for HVAC C2 LAN - 192.168.33.240/29

---

### Step 5: Determine the Fourth Largest Subnet

- Subnet description:  
  _Answer:_  BR1-BR2 Link
- Number of IP addresses required:  
  _Answer:_  4
- Subnet mask needed:  
  _Answer:_  255.255.255.252 OR /30
- Total host addresses supported:  
  _Answer:_  2
- Can the remaining subnet support this?  
  _Answer:_  YES
- Resulting network addresses:  
  _Answer:_  192.168.33.248/30    192.168.33.252/30
- Use the first network address for this subnet.
    192.168.33.248/30
---

## Part 2: Design the VLSM Address Scheme

### Step 1: Calculate Subnet Information

| Subnet Description   | Hosts Needed | Network Address /CIDR | First Host Address | Broadcast Address |
|----------------------|--------------|------------------------|--------------------|-------------------|
| BR1 LAN              | 40           |  192.168.33.128/26     | 192.168.33.129     | 192.168.33.191    |
| BR2 LAN              | 25           |  192.168.33.192/27     | 192.168.33.193     | 192.168.33.223    |
| BR2 IoT LAN          | 5            |  192.168.33.224/29     | 192.168.33.225     | 192.168.33.231    |
| BR2 CCTV LAN         | 4            |  192.168.33.232/29     | 192.168.33.233     | 192.168.33.239    |
| BR2 HVAC C2 LAN      | 4            |  192.168.33.240/29     | 192.168.33.241     | 192.168.33.247    |
| BR1-BR2 Link         | 2            |  192.168.33.248/30     | 192.168.33.249     | 192.168.33.251    |

---

### Step 2: Complete Device Interface Address Table

| Device | Interface | IP Address        | Subnet Mask       | Description        |
|--------|-----------|-------------------|-------------------|--------------------|
| BR1    | G0/0/0    | 192.168.33.249    | 255.255.255.252   | BR1-BR2 Link       |
| BR1    | G0/0/1    | 192.168.33.129    | 255.255.255.192   | 40 Host LAN        |
| BR2    | G0/0/0    | 192.168.33.250    | 255.255.255.252   | BR1-BR2 Link       |
| BR2    | G0/0/1    | 192.168.33.193    | 255.255.255.224   | 25 Host LAN        |

---

## Part 3: Cable and Configure the IPv4 Network

### Step 1: Cable the Network

- Match the topology diagram

### Step 2: Configure Basic Router Settings

- Assign hostname  
- Disable DNS lookup  
- Set encrypted privileged EXEC password: `class`  
- Set console and VTY password: `cisco`  
- Encrypt plaintext passwords  
- Create login banner

---

### Step 3: Configure Router Interfaces

- Assign IP address and subnet mask  
- Add interface descriptions  
- Activate interfaces

---

### Step 4: Save Configuration and Test Connectivity

- From BR1, ping BR2 G0/0/0  
- From BR2, ping BR1 G0/0/0  
- Troubleshoot if pings fail

**Note:** Pings to LAN interfaces may fail without routing protocols and active interfaces.

---

## Reflection Question

**Can you think of a shortcut for calculating the network addresses of consecutive /30 subnets?**  
_Answer:_  

---

## Router Interface Summary Table

| Router Model | Ethernet #1 | Ethernet #2 | Serial #1 | Serial #2 |
|--------------|-------------|-------------|-----------|-----------|
| 1800         | F0/0        | F0/1        | S0/0/0    | S0/0/1    |
| 1900         | G0/0        | G0/1        | S0/0/0    | S0/0/1    |
| 2801         | F0/0        | F0/1        | S0/1/0    | S0/1/1    |
| 2811         | F0/0        | F0/1        | S0/0/0    | S0/0/1    |
| 2900         | G0/0        | G0/1        | S0/0/0    | S0/0/1    |
| 4221         | G0/0/0      | G0/0/1      | S0/1/0    | S0/1/1    |
| 4300         | G0/0/0      | G0/0/1      | S0/1/0    | S0/1/1    |

**Note:** Interface identifiers vary by router model. This table includes common Ethernet and Serial combinations.

