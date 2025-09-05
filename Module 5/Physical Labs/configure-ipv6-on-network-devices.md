# Lab – Configure IPv6 Addresses on Network Devices

## Objectives

- **Part 1:** Set Up Topology and Configure Basic Router and Switch Settings  
- **Part 2:** Configure IPv6 Addresses Manually  
- **Part 3:** Verify End-to-End Connectivity

---

## Topology & Addressing Table

| Device | Interface   | IPv6 Address               | Prefix Length | Default Gateway |
|--------|-------------|----------------------------|----------------|------------------|
| R1     | G0/0/0      | 2001:db8:acad:a::1         | 64             | N/A              |
| R1     | G0/0/1      | 2001:db8:acad:1::1         | 64             | N/A              |
| S1     | VLAN 1      | 2001:db8:acad:1::b         | 64             | N/A              |
| PC-A   | NIC         | 2001:db8:acad:1::3         | 64             | fe80::1          |
| PC-B   | NIC         | 2001:db8:acad:a::3         | 64             | fe80::1          |

---

## Background / Scenario

In this lab, you will configure IPv6 addresses on hosts and network devices. You will use `show` commands to verify IPv6 unicast addresses and test connectivity using `ping` and `traceroute`.

---

## Required Resources

- 1 Router (Cisco 4221 or comparable)  
- 1 Switch (Cisco 2960 or comparable)  
- 2 PCs  
- Console cables  
- Ethernet cables  
- Terminal emulation software (e.g., Tera Term)

---

## Part 1: Cable the Network and Configure Basic Router and Switch Settings

### Step 1: Configure the Router

- Assign hostname  
- Configure basic settings  

### Step 2: Configure the Switch

- Assign hostname  
- Configure basic settings  

---

## Part 2: Configure IPv6 Addresses Manually

### Step 1: Assign IPv6 Addresses to R1 Interfaces

- Assign global unicast addresses to G0/0/0 and G0/0/1  
- Manually configure link-local address `fe80::1` on both interfaces  
- Use `show ipv6 interface` to verify link-local address  

**Question:**  
- Which two multicast groups are assigned to interface G0/0/0?  
  _Answer:_  ff02::2 ff02::1

---

### Step 2: Enable IPv6 Routing on R1

- Use `ipv6 unicast-routing` command  
- Use `ipconfig` on PC-B to verify IPv6 address assignment via SLAAC  

**Questions:**  
- Has an IPv6 unicast address been assigned to PC-B?  
  _Answer:_  No
- Why did PC-B receive the Global Routing Prefix and Subnet ID from R1?  
  _Answer:_  On R1, all its IPv6 interfaces joined FF02::2 that includes all routers. This lets R1 send messages to all devices on the local network. These messages tell the devices about the network address and the subnet. R1 also tells the devices that its address fe80::1 is the gateway to use. The PCs will use this info to automatically set their own IPv6 address and gateway, as long as the network part of the address is 64 bits long.

---

### Step 3: Assign IPv6 Addresses to S1 Management Interface

- Assign global unicast and link-local address  
- Use `show ipv6 interface` to verify configuration  

---

### Step 4: Assign Static IPv6 Addresses to PCs

- Configure static IPv6 addresses via Ethernet Properties  
- Verify each PC has both static and SLAAC-assigned global IPv6 addresses  

---

## Part 3: Verify End-to-End Connectivity

- From PC-A, ping `fe80::1` (R1 G0/0/1)  
- Ping S1 management interface from PC-A  
- Use `tracert` from PC-A to PC-B  
- From PC-B, ping PC-A  
- From PC-B, ping `fe80::1` (R1 G0/0/0)

**Note:** If connectivity fails, verify IPv6 address assignments on all devices.

---

## Reflection Questions

1. Why can the same link-local address `fe80::1` be assigned to both Ethernet interfaces on R1?  
   _Answer:_  fe80::1 can be used in multiple ethernet interfaces in a router because it is only required to be unique or different within a single link. So because it is used on G0/0/0 does not mean that it is the same when used on G0/0/1.

2. What is the Subnet ID of the IPv6 unicast address `2001:db8:acad::aaaa:1234/64`?  
   _Answer:_  The subnet ID address is 0000 because its the fourth hextet in the subnet ID of the ipv6 address. In this case it is "::" meaning "0000" So that is the subnet ID.

---

## Router Interface Summary Table

| Router Model | Ethernet Interface #1 | Ethernet Interface #2 | Serial Interface #1 | Serial Interface #2 |
|--------------|------------------------|------------------------|----------------------|----------------------|
| 1800         | Fast Ethernet 0/0      | Fast Ethernet 0/1      | Serial 0/0/0         | Serial 0/0/1         |
| 1900         | Gigabit Ethernet 0/0   | Gigabit Ethernet 0/1   | Serial 0/0/0         | Serial 0/0/1         |
| 2801         | Fast Ethernet 0/0      | Fast Ethernet 0/1      | Serial 0/1/0         | Serial 0/1/1         |
| 2811         | Fast Ethernet 0/0      | Fast Ethernet 0/1      | Serial 0/0/0         | Serial 0/0/1         |
| 2900         | Gigabit Ethernet 0/0   | Gigabit Ethernet 0/1   | Serial 0/0/0         | Serial 0/0/1         |
| 4221         | Gigabit Ethernet 0/0/0 | Gigabit Ethernet 0/0/1 | Serial 0/1/0         | Serial 0/1/1         |
| 4300         | Gigabit Ethernet 0/0/0 | Gigabit Ethernet 0/0/1 | Serial 0/1/0         | Serial 0/1/1         |

**Note:** Use interface identifiers to determine router configuration. This table includes common Ethernet and Serial interface combinations.

