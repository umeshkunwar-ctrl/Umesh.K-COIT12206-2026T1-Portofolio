# GNS3 Multi-Host Network Configuration Project

##  Author
**Umesh Kunwar**  
Student ID: 12301486  
Subject:COIT12206 Sydney
Date: 15/03/2026  

---

##  Project Overview
This project demonstrates a multi-host network configuration using GNS3.  
Four hosts are connected through a switch, configured with static IP addresses, and tested for connectivity using Linux networking commands.

---

##  1. Network Topology
![Topology](week2intro.png)
![Topology](Config-host1.png)
![Topology](Config-host2.png)
![Topology](console-host4.png)


### Description:
The network consists of:
- 4 Hosts (Host1, Host2, Host3, Host4)
- 1 Switch (Switch1)

Each host is connected to the switch using Ethernet interfaces.  
This setup represents a basic LAN (Local Area Network).

---




### Description:
A new project was created in GNS3.  
This step initializes the workspace where all devices and configurations are added.

---

##  3. Host Configuration (Static IP)
![Host Config](ip-host3.png)
![Host Config](ip-host4.png)

## Ping (connectivity)
![Host Config](Ping-success-1to2.png)
![Host Config](ping-success.png)
### Description:
Each host was configured with a static IP address by editing:

```bash
/etc/network/interfaces
auto eth0
iface eth0 inet static
    address 10.10.2.x
    netmask 255.255.255.0
ip address show
ping 10.10.2.2
ping 10.10.2.5
nc -l -p 12345
echo "hello" | nc <IP_ADDRESS> 12345


