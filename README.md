# Routing and Switching: an exploration of CCNA-level networking concepts
All projects were created in Cisco Packet Tracer. All network topologies and network device configurations were created and written by myself. 

<br> <br> 

## Inter-VLAN Routing  

This lab demonstrates a 'router-on-a-stick' configuration, which allows for traffic to be routed between separate VLANs through configuring multiple logical sub-interfaces over a single physical interface.  

By configuring inter-VLAN routing, communication between VLANs is enabled, while still retaining the core benefits of VLANs; improved network segmentation, reduced broadcast traffic and better network security and isolation between departments.

### Objective 
All PCs must be able to successfully ping each other from different VLANs, subnets or networks.


### Network Topology

![inter vlan routing 3](https://github.com/user-attachments/assets/bcf72ef4-9ffc-4295-954a-fa91dac094cd)


### Network Breakdown

![image](https://github.com/user-attachments/assets/6421fee3-49e2-4d5d-9421-81c8bb4451bd)

### Tasks carried out:

- Appropriate IP addresses assigned to PCs statically.
- Default gateways set as the last usable IP address within a subnet.
- Trunk links configured between both switches and also the router.
- VLANs configured on both swithces and appropriately named (Sales, Engineering, Security).
- Switchports connecting to end-user devices were configured as access ports and assigned to the relevant VLANs.
- Three sub-interfaces were configured on the router to match each subnet and allow inter-VLAN routing.
- Connectivity was verified by ensuring all PCs were able to ping each other.  

 <br> <br> <br> 
 
## DHCP Server Configuration  
In this lab, a DHCP server is configured to automatically assign IP addresses to devices across several different VLANs. A router-on-a-stick configuration allowed for devices in different
VLANS/subnets to ping each other via inter-VLAN routing.

### Objective
For devices in VLAN 10, 20 and 30 to receive IP addresses from DHCP server based in VLAN 30 (70.4.2.5).

### Network Topology 

![intervlan routing + DHCP server](https://github.com/user-attachments/assets/994741f1-4e11-4f93-9c8f-7e0b92e4a9cb)

### Network Breakdown

![image](https://github.com/user-attachments/assets/c0fe19ff-8838-450c-9372-97d8914531d6)


### Tasks Carried Out

- Subnets were created and default gateways set as the last usable IP address of each subnet.
- Trunk links were configured between the switches and the router.
- Three separate sub-interfaces were configured on the router to match each subnet and allow inter-VLAN routing.
- VLANs were configured and named on each switch (Security, Engineering and HR).
- All switchports connecting to end-user devices were configured as access ports and assigned to the relevant VLANs.
- A DHCP server was added to the 70.4.2.0/28 subnet (70.4.2.5).
- DHCP address pools were configured for each VLAN. The default gateway was set as the last usable IP address within the address pool.
- 'Pool 1: Security' was configured with the address range 10.25.2.1 - 10.25.2.14.
- 'Pool 2: Engineering' was configured with the address range 192.168.7.1 - 192.168.7.6.
- 'Pool 3: HR' was configured with the address range 70.4.2.1 - 70.4.2.14.

<br> <br> <br> 

## OSPF Configuration
This project demonstrates the use of Open Shortest Path First (OSPF); a dynamic link-state routing protocol that is frequently used in enterprise networks to facilitate dynamic routing. Each router is configured to operate within the network backbone (Area 0) and all routes are advertised within one single Autonomous-System.

### Objective 
For each router to establish a full-neighbor-adjacency with the other routers and for routing information to be exchanged through link-state-advertisements. All PCs must be able to ping each other in order to verify connectivity and that dynamic routing is working as expected.

### Network Topology

![OSPF2](https://github.com/user-attachments/assets/dd73eeb0-9c73-4225-a955-50b8e47813eb)

### Network Breakdown

![image](https://github.com/user-attachments/assets/7a066016-2787-4c42-9169-6513e7e9669a)


### Tasks Carried Out

- Connected the devices by ethernet cable and configured router interfaces with appropriate subnets, IP addresses and subnet masks. Router interfaces were enabled once basic configurations were complete.
- Enabled OSPF routing on all routers.
- Advertised each directly connected network by using 'network' commands and the appropriate wildcard subnet masks (each network was advertised within the network backbone of Area 0).
- Verified that OSPF neighbor adjacencies had been established between all routers. Routing tables were checked on each router to verify this.
- Connectivity between hosts was tested to verify that dynamic routing was in place and working as expected.
