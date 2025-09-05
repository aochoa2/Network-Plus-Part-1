# 📘 Assignment: Number Systems in IT and Networking
Aida Ochoa
9/4/25

## 🧠 Overview

In Information Technology, understanding number systems is essential for working with data, memory, and networking. Two key number systems used in IT are:

- **Binary (Base-2)**: Uses only 0 and 1. It is the fundamental language of computers.
- **Hexadecimal (Base-16)**: Uses digits 0–9 and letters A–F. It is often used for compact representation of binary data.

These systems are especially important in networking, where they are used in:

- **IPv4 addresses** (e.g., `192.168.1.1`)
- **IPv6 addresses** (e.g., `2001:0db8:85a3:0000:0000:8a2e:0370:7334`)
- **MAC addresses** (e.g., `00:1A:2B:3C:4D:5E`)

---

## 🔢 Binary and Hexadecimal Basics

### Binary (Base-2)
Each digit represents a power of 2. For example:
Binary: 1101 Decimal: (1×8) + (1×4) + (0×2) + (1×1) = 13

### Hexadecimal (Base-16)
Each digit represents a power of 16. For example:
Hex: 1A Decimal: (1×16) + (10×1) = 26

### Conversion Tips

- **Binary to Hex**: Group binary digits into sets of 4 (from right to left), then convert each group to hex.
- **Hex to Binary**: Convert each hex digit to its 4-bit binary equivalent.

---

## 🌐 Networking Applications

### IPv4 Addresses
IPv4 addresses are typically shown in decimal, but each octet (e.g., `192`) can be converted to binary for subnetting and routing.

**Example:**
IPv4: 192.168.1.1 
Binary: 11000000.10101000.00000001.00000001

### IPv6 Addresses
IPv6 addresses are written in hexadecimal and are 128 bits long.

**Example:**
IPv6: 2001:0db8:85a3:0000:0000:8a2e:0370:7334 
Binary: Each hex digit = 4 bits → 32 hex digits = 128 bits

### MAC Addresses
MAC addresses are 48-bit identifiers written in hexadecimal.

**Example:**
MAC: 00:1A:2B:3C:4D:5E 
Binary: 00000000 00011010 00101011 00111100 01001101 01011110

---

## 📝 Exercises

### Exercise 1: Binary to Decimal
Convert the following binary numbers to decimal:
1. `1010` = 10
2. `11110000` = 240
3. `00001111` = 15

### Exercise 2: Decimal to Binary
Convert the following decimal numbers to binary:
1. `25` = 11001
2. `192` = 11000000
3. `255` = 11111111

### Exercise 3: Binary to Hexadecimal
Convert the following binary numbers to hexadecimal:
1. `11010111` = DA
2. `10101010` = AA
3. `11111111` = FF

### Exercise 4: Hexadecimal to Binary
Convert the following hexadecimal numbers to binary:
1. `1F` = 00011111
2. `A3` = 10100011
3. `FF` = 11111111

### Exercise 5: IPv4 Binary Conversion
Convert the IPv4 address `172.16.254.1` to binary.
10101100.00010000.11111110.00000001

### Exercise 6: MAC Address Binary Conversion
Convert the MAC address `DE:AD:BE:EF:00:01` to binary.
11011110 : 10101101 : 10111110 : 11101111 : 00000000 : 00000001

