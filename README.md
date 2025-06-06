# Routing and Switching: an exploration of CCNA-level networking concepts
All projects were created in Cisco Packet Tracer. All network topologies and device configurations were created and written by myself. 


## Inter-VLAN Routing
This lab demonstrates the configuration of multiple VLANs on a switch and the ability to route between different VLANs through a 'router-on-a-stick' configuration using virtual sub-interfaces.
Appropriate IP addresses were configured for each device and these were then placed within relevant subnets. 


### Objective 
All PCs must be able to successfully ping each other from different subnets and VLANs.


## Topology




![inter vlan routing](https://github.com/user-attachments/assets/2d566474-bf32-4f21-a12f-da201ec3d362)


#### Router 1 ROAS Configuration:

interface GigabitEthernet0/0/0.10  
encapsulation dot1Q 10  
ip address 10.1.1.6 255.255.255.240  

interface GigabitEthernet0/0/0.20  
encapsulation dot1Q 20  
ip address 10.1.2.6 255.255.255.240  

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
 switchport access vlan 10  
 switchport mode access  
 
