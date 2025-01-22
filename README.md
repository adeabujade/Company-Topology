<p align="center">
</p>

<h1>Cisco Packet Tracer |  Company Topology<h1>
  
This report outlines the design and implementation of a hierarchical network topology to support a new three-floor building. The network will ensure redundancy, scalability, and efficient communication across departments while maintaining robust security. The design also includes integration with two ISPs for internet connectivity and redundancy.

<h2>Environments and Technologies Used</h2>

- Cisco Packet Tracer

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>Objectives</h2>

-Provide seamless and secure communication across all departments.

-Ensure redundancy at every network layer using two routers and two multilayer switches.

-Enable dynamic IP address allocation for all devices except for those in the server room, which will use static IP addresses.

-Support inter-VLAN communication through multilayer switches configured for routing and switching functionalities.

-Facilitate wireless connectivity for users in each department.

-Maintain continuous internet access through dual ISP connections.


<h2>Network Design Implementation</h2>

<p>

</p>
<p>
<h2>1. Network Topology and Reduncacy</h2>

Network Topology and Redundancy

Core Layer:
Two routers will be deployed to connect the internal network to the internet via two ISPs. Each router will connect to one ISP using the following public IP subnets:


ISP1: 195.136.17.0/30 and 195.136.17.4/30

ISP2: 195.136.17.8/30 and 195.136.17.12/30

Static routes will be configured for external connectivity.
Distribution Layer:

Two multilayer switches will provide redundancy and handle inter-VLAN routing. Both switches will be interconnected and configured for High Availability (HA).

The switches will connect to the core routers and the access switches for each floor.

Access Layer:
Each floor will have access switches to connect end-user devices and wireless access points.

Department and Floor Configuration
First Floor:

Departments: Sales and Marketing, Human Resources, and Logistics.

Users: 120 per department.

VLANs:
VLAN 10: Sales and Marketing

VLAN 20: Human Resources and Logistics

IP Subnets:

VLAN 10: 172.16.1.0/25

VLAN 20: 172.16.1.128/25

Second Floor
Departments: Finance and Accounts, Administrator, and Public Relations.

Users: 120 per department

VLANs:

VLAN 30: Finance and Accounts

VLAN 40: Administrator and Public Relations

IP Subnets:

VLAN 30: 172.16.2.0/25

VLAN 40: 172.16.2.128/25

Third Floor
Departments: ICT, Server Room.

Users:
ICT: 120 users

Server Room: 12 devices (static IPs)

VLANs:

VLAN 50: ICT

VLAN 60: Server Room

IP Subnets:

VLAN 50: 172.16.3.0/25

VLAN 60: 172.16.3.128/28 (for static IP allocation)

![image](https://github.com/user-attachments/assets/6598ad01-a156-4746-9a43-85de9f94f955)

</p>
<br />

<p>

</p>
<p>
<h2>.2 DHCP and Static IP Allocation</h2>
To enable communication between routers and ensure efficient route advertisement, OSPF (Open Shortest Path First) was configured. The following configurations were implemented:
Each router was assigned to OSPF process 1.
Subnets associated with each router’s interfaces were advertised using the network command.

**Core Router 1 IP Routes**

![image](https://github.com/user-attachments/assets/ac273ea6-7c6b-45a0-9cd2-05b67af23f58)

**Core Router 2 IP Routes**


![image](https://github.com/user-attachments/assets/c82f7077-c970-4d3d-8e8a-435e6200ef8f)



</p>
<br />
</p>
<br />

<p>

</p>
<p>
<h2>3. Device Settings</h2>
  
Basic device settings will be configured on all routers and switches:

-Hostnames for identification.

  a.By using hostname configuration
  
-Console and enable passwords for secure access.

  a.By using username admin password 7 configuration 
  
-Banner messages for unauthorized access warnings.

  a.No Unauthorized Access will be displayed on all router and switches if attempted to login


</p>
<br /></p>
<br />

<p>

</p>
<p>
<h2>4.VLANs </h2>
  
-Multilayer switches will handle inter-VLAN routing by being assigned IP addresses on each VLAN interface.
-Inter-VLAN communication will be verified through proper route configurations and testing.

**Multilayer Switch 1 VLANs**


![image](https://github.com/user-attachments/assets/4b75ddb2-b7fd-40e2-9b33-7ba67dc2681a)

**Multilayer Switch 2 VLANs**


![image](https://github.com/user-attachments/assets/328d672d-9ea9-49ff-8d75-4fc56da95640)

</p>
<br />
</p>
<br /></p>
<br />

<p>

</p>
<p>
<h2>7. Testing</h2>
  
-Test inter-VLAN communication using ping tests between devices in different VLANs.

**HR PC to ISP2**

![image](https://github.com/user-attachments/assets/f8dade28-56c5-41ea-a929-00f179cdcf7b)

**ICT PC to ISP1**

![image](https://github.com/user-attachments/assets/2a92d716-a2a9-482c-858c-93f817113f0a)

**Sales PC to Admin PC**S

![image](https://github.com/user-attachments/assets/9d21bccc-c280-4ccc-bce5-dd0bb8168c78)


</p>
<br /></p>
<br /></p>
<br />

<p>

</p>
<p>
<h2>Conclusion</h2>
This hierarchical network design ensures redundancy, scalability, and secure communication across all departments in the new building. By integrating VLANs, DHCP, inter-VLAN routing, and dual ISP connectivity, the network meets the requirements for performance and reliability. Proper testing and verification will ensure the network functions as expected, supporting current and future needs.

</p>
<br />
