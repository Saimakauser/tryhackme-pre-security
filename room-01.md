# FREE ROOM
# Task 1 — What is Networking?

**Question:** What is the key term for devices that are connected together?

**Answer:** The key term for devices that are connected together is **Network**.

**Short explanation:**  
A **network** is a collection of devices (for example: computers, phones, cameras, traffic lights) that are linked so they can share information and resources. Networks can be as small as two devices or as large as billions of devices. They are used in many areas of life — public transport systems, power grids, postal systems — and are essential in computing and cybersecurity because they allow devices to communicate and exchange data.

# Task 2 — What is the Internet?

**Question:** Who invented the World Wide Web?

**Answer:** The World Wide Web was invented by **Tim Berners-Lee** in 1989.

**Short explanation:**  
The **Internet** is a giant network made up of many smaller networks. It allows devices all over the world to communicate with each other. Originally, the idea of the Internet began with the **ARPANET project** in the late 1960s, funded by the U.S. Department of Defense. But the Internet became what we know today in 1989 when **Tim Berners-Lee** created the **World Wide Web (WWW)**. The WWW made it possible to store, share, and access information easily across the Internet.  

In short:  
- **Private networks** = Small, local networks.  
- **Public network (Internet)** = The global connection of many private networks.  

# Task 3 — Identifying Devices on a Network

**Topic summary:**  
To communicate reliably on a network, devices must be both *identifying* and *identifiable*. Like humans have names and fingerprints, devices have two main identifiers:

- **IP Address** — like a name that can change over time (assigned to a device while it's on a network).  
- **MAC Address** — like a fingerprint or serial number assigned to the network interface at the factory (usually permanent, 12-character hexadecimal).


## IP Addresses (brief)
- An IP address is made up of **four octets** (IPv4), e.g. `192.168.1.77`.  
- Private IPs identify devices inside a local network.  
- Public IPs identify devices on the Internet (assigned by ISP).  
- IPv4 uses 2³² addresses (~4.29 billion). IPv6 uses 2¹²⁸ addresses (vastly more).

Example device mapping:

| Device Name       | IP Address     | IP Address Type |
|-------------------|----------------|-----------------|
| DESKTOP-KJE57FD   | 192.168.1.77   | Private         |
| DESKTOP-KJE57FD   | 86.157.52.21   | Public          |
| CMNatic-PC        | 192.168.1.74   | Private         |
| CMNatic-PC        | 86.157.52.21   | Public          |

Images (from TryHackMe):  
- ![img1](https://assets.tryhackme.com/additional/cmn-aoc2020/day-8/1.png)  
- ![img2](https://assets.tryhackme.com/additional/cmn-aoc2020/day-8/2.png)

## MAC Addresses (brief)
- MAC = **Media Access Control** address.  
- Format: twelve hexadecimal characters separated by colons, e.g. `a4:c3:f0:85:ac:2d`.  
- First 6 hex = manufacturer OUI, last 6 hex = unique NIC id.  
- MACs can be **spoofed** (faked). Spoofing can bypass poorly designed security mechanisms that rely solely on MAC filtering.

**Practical lab note:** The interactive lab simulates hotel Wi-Fi that only allows packets from paid MAC addresses. Try spoofing Bob's MAC to Alice's to see access granted.


## Questions & Answers

**Q:** What does the term "IP" stand for?  
**A:** **Internet Protocol**

**Q:** What is each section of an IP address called?  
**A:** **Octet**

**Q:** How many sections (in digits) does an IPv4 address have?  
**A:** **4**

**Q (Hint):** What does the term "MAC" stand for?  
**A:** **Media Access Control**

**Q (Lab):** Deploy the interactive lab and spoof your MAC address to access the site. What is the flag?  
**A:** `THM{YOU_GOT_ON_TRYHACKME}`


# Task 4 — Ping (ICMP)

**Topic summary:**  
Ping is a simple but powerful network tool that uses the **ICMP (Internet Control Message Protocol)** to check if a device is reachable and how fast the connection is.  
- It sends an **ICMP Echo Request** to a target.  
- If the target is reachable, it replies with an **ICMP Echo Reply**.  
- Ping reports details such as packet loss and round-trip time (RTT) in milliseconds.  

**Common use:**  
- Test if a device/website is online.  
- Measure response time (latency).  
- Troubleshoot network connectivity.  

**Syntax example:**  
```bash
ping 10.10.10.10
Screenshot reference (TryHackMe shows 192.168.1.254 being pinged, average ~4.16ms).

Questions & Answers
Q: What protocol does ping use?
A: ICMP

Q: What is the syntax to ping 10.10.10.10?
A: ping 10.10.10.10

Q: What flag do you get when you ping 8.8.8.8?
A: THM{I_PINGED_THE_SERVER}

Key Takeaways (Tasks 1–4)

#Task 1 — Networking
A network is a group of connected devices (from 2 to billions).
Purpose: share resources, data, and communicate.
Networks exist everywhere: computers, phones, traffic systems, electricity grids.
Keyword: Network = devices connected together.

#Task 2 — The Internet
The Internet = giant global network of smaller networks
Two main types of networks:
Private network (local, e.g., home/office).
Public network (the Internet).
Invented:
ARPANET (1960s) was the foundation of the Internet.
Keyword: Internet = network of networks.

#Task 3 — Identifying Devices on a Network
Devices have two identifiers:
IP Address (temporary, can change, identifies device on network).
MAC Address (permanent hardware address, unique per device).
IPv4: 4 octets (e.g., 192.168.1.1).
IPv6: supports far more addresses.
MAC addresses can be spoofed (pretending to be another device).
Keyword: IP = Internet Protocol, MAC = Media Access Control.

#Task 4 — Ping (ICMP)
Ping checks if a device is reachable and measures connection quality.
Uses ICMP (Internet Control Message Protocol).
Syntax: ping [IP/URL]
Revealed flag: THM{I_PINGED_THE_SERVER}
Keyword: Ping = ICMP Echo Request + Reply.

