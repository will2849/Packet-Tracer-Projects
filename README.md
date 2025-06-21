# Routing and Switching: an exploration of CCNA-level networking concepts
All projects were created in Cisco Packet Tracer.


## Inter-VLAN Routing
This lab demonstrates the configuration of multiple VLANs on a switch and the ability to route between different VLANs through a 'router-on-a-stick' configuration using virtual sub-interfaces.
Appropriate IP addresses were configured for each device and these were then placed within relevant subnets. 


## Objective 
All PCs must be able to successfully ping each other from different VLANs, subnets or networks.


## Topology

![inter vlan routing 3](https://github.com/user-attachments/assets/bcf72ef4-9ffc-4295-954a-fa91dac094cd)


## Network Breakdown

![image](https://github.com/user-attachments/assets/6421fee3-49e2-4d5d-9421-81c8bb4451bd)

## Tasks carried out:

- Appropriate IP addresses assigned to PCs statically.
- Default gateways set as the last usable IP address within a subnet.
- Trunk links configured between both switches and also the router.
- VLANs configured on both swithces and named (Sales, Engineering, Security).
- Switch ports connecting to PCs were configured as access ports and assigned to the relevant VLANs.
- Three sub-interfaces were configured on the router to match each subnet and allow inter-VLAN routing.
- Verified connectivity by ensuring all PCs were able to ping each other. 

### Device Running-Configs

#### Router 1 ROAS Configuration:

interface GigabitEthernet0/0/0.10  
encapsulation dot1Q 10  
ip address 10.1.1.14 255.255.255.240  

interface GigabitEthernet0/0/0.20  
encapsulation dot1Q 20  
ip address 10.1.2.14 255.255.255.240  

interface GigabitEthernet0/0/0.30  
 encapsulation dot1Q 30  
 ip address 10.1.1.30 255.255.255.240  

#### Switch 1 Configuration:  
interface FastEthernet0/1  
 switchport mode trunk  
!  
interface FastEthernet0/2  
 switchport mode trunk  
!  
interface FastEthernet0/3  
 switchport access vlan 10  
 switchport mode access  
!  
interface FastEthernet0/4  
 switchport access vlan 20  
 switchport mode access  
!  
interface FastEthernet0/5  
 switchport access vlan 20  
 switchport mode access  

 #### Switch 2 Configuration:

interface FastEthernet0/1  
 switchport mode trunk  
!  
interface FastEthernet0/2  
 switchport access vlan 10  
 switchport mode access  
!  
interface FastEthernet0/3  
 switchport access vlan 20  
 switchport mode access  
!  
interface FastEthernet0/4  
 switchport access vlan 10  
 switchport mode access  
!  
interface FastEthernet0/5  
 switchport access vlan 10  
 switchport mode access  
!  
interface FastEthernet0/6  
 switchport access vlan 30  
 switchport mode access  
!  
interface FastEthernet0/7  
 switchport access vlan 30  
 switchport mode access  
!  
interface FastEthernet0/8  
 switchport access vlan 30  
 switchport mode access  
 
## DHCP Server Configuration
In this lab, a DHCP server is configured to automatically assign IP addresses to devices across several different VLANs. A router-on-a-stick configuration allows for devices in different
VLANS/subnets to ping each other via inter-VLAN routing.

## Objective
For devices in VLAN 10 and VLAN 30 to receive IP addresses from DHCP server based in VLAN 20 (70.4.2.5).

## Topology 

![intervlan routing + DHCP server](https://github.com/user-attachments/assets/994741f1-4e11-4f93-9c8f-7e0b92e4a9cb)

## Network Breakdown

![image](https://github.com/user-attachments/assets/c0fe19ff-8838-450c-9372-97d8914531d6)


## Tasks Carried Out
