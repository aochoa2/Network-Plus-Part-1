# 7.3.7 Lab - View the Switch MAC Address Table

## Topology & Addressing Table

| Device | Interface | IP Address     | Subnet Mask     |
|--------|-----------|----------------|------------------|
| S1     | VLAN 1    | 192.168.1.11   | 255.255.255.0    |
| S2     | VLAN 1    | 192.168.1.12   | 255.255.255.0    |
| PC-A   | NIC       | 192.168.1.1    | 255.255.255.0    |
| PC-B   | NIC       | 192.168.1.2    | 255.255.255.0    |

---

## Objectives

- **Part 1:** Build and Configure the Network  
- **Part 2:** Examine the Switch MAC Address Table

---

## Part 1: Build and Configure the Network

### Step 1: Cable the network according to the topology

**Screenshot Placeholder:**  
![alt text](image-8.png)

---

### Step 2: Configure PC hosts

**Screenshot Placeholder:**  
`![PC Configuration](path/to/sStep 3: Initialize and reload switches as necessary

**Screenshot Placeholder:**  
![alt text](image-9.png)
![alt text](image-10.png)

---

### Step 4: Configure basic settings for each switch

- **Device name**  
- **IP address**  
- **Console and vty passwords: `cisco`**  
- **Privileged EXEC password: `class`**

---

## Part 2: Examine the Switch MAC Address Table

### Step 1: Record network device MAC addresses

1. **PC-A MAC Address:**  
   _Answer:_  0001.974A.2588

2. **PC-B MAC Address:**  
   _Answer:_  0050.0F25.6B56

3. **S1 Fast Ethernet 0/1 MAC Address:**  
   _Answer:_  0060.2f40.7101

4. **S2 Fast Ethernet 0/1 MAC Address:**  
   _Answer:_  00d0.974e.d901

---

### Step 2: Display the switch MAC address table

1. **Are there any MAC addresses recorded in the MAC address table?**  
   _Answer:_  No

2. **What MAC addresses are recorded in the table? To which switch ports are they mapped and to which devices do they belong?**  
   _Answer:_  I had to do this assignment on Packet Tracer, so there were no MAC addresses recorded on the table.

3. **If you had not previously recorded MAC addresses of network devices in Step 1, how could you tell which devices the MAC addresses belong to using only the output from `show mac address-table`? Does it work in all scenarios?**  
   _Answer:_  The "show mac address-table"command shows which port a device is connected to. Just like many things, some things don't always work.

---

### Step 3: Clear the S2 MAC address table and display the MAC address table again

1. **Does the MAC address table have any addresses in it for VLAN 1? Are there other MAC addresses listed?**  
   _Answer:_  No

2. **Wait 10 seconds and recheck. Are there new addresses in the MAC address table?**  
   _Answer:_  No

---

### Step 4: From PC-B, ping the devices on the network and observe the switch MAC address table

1. **How many device IP-to-MAC address pairs have been learned by ARP (excluding multicast/broadcast)?**  
   _Answer:_  No arp entries found

2. **Did all devices have successful replies to pings? If not, check cabling and IP configurations.**  
   _Answer:_  No

3. **Has the switch added additional MAC addresses to the MAC address table? If so, which addresses and devices?**  
   _Answer:_  No

4. **Does the PC-B ARP cache have additional entries for all network devices that were sent pings?**  
   _Answer:_  No

---

## Reflection Question

**What might be some of the challenges on larger networks when switches and PCs dynamically build ARP caches and MAC address tables?**  
_Answer:_  On larger networks, the mac address and arp tables are always updating and can cause issues when forwarding data. There might not be enough storage to store all this data either and could potentially crash with a lot going on.
