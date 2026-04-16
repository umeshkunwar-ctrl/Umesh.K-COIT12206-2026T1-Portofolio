# VLAN Configuration using Open vSwitch (GNS3)

##  Author
Umesh Kunwar  
Student ID: 12301486  

---

## Project Overview
This project demonstrates VLAN configuration using Open vSwitch (OVS) in GNS3.  
Hosts are divided into different VLANs and communication is controlled using tagging and trunking.

---

##  1. Network Topology
![Topology](topology.png)

### Description:
- Two VLAN groups:
  - VLAN 491 → Host1, Host2
  - VLAN 492 → Host3, Host4
- All hosts are connected through a switch
- Each VLAN represents a separate logical network

---

##  2. Task 2 Topology with Router
![Task2](task2-topology.png)

### Description:
A router is introduced to enable communication between VLANs.  
This is required because VLANs cannot communicate directly.

---

##  3. Open vSwitch Initialization
![OVS Init](ovs-init.png)

### Description:
OVS was started using:

```bash
sh /etc/openvswitch/init.sh
ovs-vsctl set port eth1 tag=491
ovs-vsctl set port eth2 tag=491
ovs-vsctl set port eth3 tag=492
ovs-vsctl set port eth4 tag=492
ping 10.10.1.102
ip neigh show
ovs-vsctl show
ip link add link eth0 name eth0.491 type vlan id 491
ip link add link eth0 name eth0.492 type vlan id 492
ping 10.10.2.104


