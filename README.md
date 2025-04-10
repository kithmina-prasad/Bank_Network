# Design and Implementation of an Enterprise Bank network

## Scenario:
Celestia Bank Ltd. is a US-owned company that deals with Banking and Insurance. The company intends to expand its services across the African continent having the first branch to be located in Nairobi, Kenya. The company has secured a four-story building to operate within the Kenyan capital city. Therefore, the company would like to allow sourcing knowledge from a group of final-year students from the local university to design and implement their company network. Assume you are among the students to take over this role, carefully read down the requirements then model the design and implement the network based on the company's needs. Each floor has departments as provided in the table below:

<img width="470" alt="image" src="https://github.com/user-attachments/assets/ef6f6915-0b19-4e4b-bc4b-f4feebb34796" />

## Requirements:

•	Use a software modeling tool to visualize the network topology (Use Hierarchical Network Design. Software Modelling Tools: MS Visio, Visual Paradigm, or Draw.io for modeling network design.

•	Use any of the following network simulation software to implement the above topology. Simulation software: Cisco Packet tracer or GNS3 for design and implementation.
  
•	Use OSPF as the routing protocol to advertise routes.

•	Each department is required to have a wireless network for the users.

•	Each department except the server room will be anticipated to have around 60 users both wired and wireless users.

•	Host devices in the network are required to obtain IPv4 addresses automatically.

•	Devices in all the departments are required to communicate with each other.

•	Create HTTP, and E-mail servers.

•	All devices in the network are expected to obtain an IP address dynamically from the dedicated DHCP servers located at the server room.

•	Configure SSH in all the routers for remote login.

•	Configure the basic configuration of the devices: Hostnames, Line Console and Enable passwords, Banner messages Disable domain IP lookup, encrypt all configured passwords.

•	Each department should be in a different VLAN and subnetwork; VLANs you will use in your case, e.g. 10, 20, 30, etc..

•	Planning of IP Addresses: You have been given 192.168.10.0 as the base address for this network. Do subnetting based on the number of hosts in every department as provided above. Identify subnet mask, useable IP address range, and broadcast address for each subnet.

•	End Device Configurations: Configure all the end devices in the network with the appropriate IP address based on the calculations above.

•	Configure port-security: Use sticky command to obtain MAC Address and Violation mode of the shutdown.

•	Test and Verifying Network Communication.

## Technologies Implemented

1.	Creating a network topology using Cisco Packet Tracer.
2.	Hierarchical Network Design.
3.	Connecting Networking devices with Correct cabling.
4.	Configuring Basic device settings.
5.	Creating VLANs and assigning ports VLAN numbers.
6.	Subnetting and IP Addressing.
7.	Configuring Inter-VLAN Routing on the Multilayer switches (Switch Virtual Interface).
8.	Configuring Dedicated DHCP Server device to provide dynamic IP allocation.
9.	Configuring SSH for secure Remote access.
10.	Configuring OSPF as the routing protocol.
11.	Configuring switchport security or Port-Security on the switches.
12.	Configuring WLAN or wireless network (Cisco Access Point).
13.	Host Device Configurations.
14.	Test and Verifying Network Communication.

## Network Model Design:

<img width="1339" alt="image" src="https://github.com/user-attachments/assets/b2a0a1e8-80b6-48cc-a081-41bf46178414" />

## Subnetting the network:

Base Network: 192.168.10.0/24 (Class C )

No of Hosts in Each Department: 60 

Subnet Size=2^n−2 -----> n - host bits

2^n−2 >= 60 -----> Therefore: n = 6

New Subnet Mask= 32-6 = /26 - 255.255.255.192


## IP Addressing

<img width="697" alt="image" src="https://github.com/user-attachments/assets/34c84a17-29dd-4018-9af9-bc4a4e1ce7e0" />

<img width="697" alt="image" src="https://github.com/user-attachments/assets/95f49cb1-b27b-4412-b5ea-f11716908b9d" />

## Between routers and layer 3 switches: 

Base Network Address: 10.10.10.0

<img width="697" alt="image" src="https://github.com/user-attachments/assets/d8cca043-f08c-49b7-8303-3fb9e76b9022" />

## Configuration:

Basic Configurations on Access switches/L3 Switches and Routers:

### Configuring access layer switches:

Floor1-Management-SW

![F1-MGT](https://github.com/user-attachments/assets/49142dba-6239-4116-9c04-425c5921a781)

Floor1-Research-SW

![F1-Research](https://github.com/user-attachments/assets/50b411e1-687d-443f-bfce-a9b6ead7458b)

Floor1-HR-SW

![F1-HR](https://github.com/user-attachments/assets/190e00c1-92ce-4d18-a84c-084d396271f3)

Floor2-Marketing-SW

![F2-MKT](https://github.com/user-attachments/assets/342ad7cb-14a5-47b4-8d50-636b2e28c99a)

Floor2-Accounting-SW

![F2-ACC](https://github.com/user-attachments/assets/75cdbcaf-e657-4146-85ac-9bf1b2b6e500)

Floor2-Finance-SW

![F2-FIN](https://github.com/user-attachments/assets/464caa10-1860-45da-bd6d-69a0b5e4b28e)

Floor3-Logistics-SW

![F3-LOG](https://github.com/user-attachments/assets/d8fbdd97-a607-477f-9ad0-3e1394e8d52c)

Floor3-Customer-SW

![F3-CUST](https://github.com/user-attachments/assets/4712a1a1-950a-45d2-9435-4582e0e10cdd)

Floor3-Guest-SW

![F3-Guest](https://github.com/user-attachments/assets/0325059e-c0b1-4d6d-ba52-6e5733bf33ed)

Floor4-Admin-SW

![F4-Admin](https://github.com/user-attachments/assets/d06c1fe1-69cb-4fd4-89f0-96916fc7e13a)

Floor4-IT-SW

![F4-IT](https://github.com/user-attachments/assets/d74ad6d1-3f03-4c36-a4ce-280e88f7d45e)

Floor4-Server-SW

![F4-Server](https://github.com/user-attachments/assets/d8ad7df9-ca73-46b6-bec4-b2f7acf1635d)



### Configuring Distribution layer switches:

Floor1-L3SW

![F1-L3SW](https://github.com/user-attachments/assets/1cd28d9c-c487-498d-8d3b-3b236a019854)

Floor2-L3SW

![F2-L3SW](https://github.com/user-attachments/assets/0128f3fe-43de-4e3b-9f02-cd846d9824c2)

Floor3-L3SW

![F3-L3SW](https://github.com/user-attachments/assets/a830a485-7147-45d4-b540-115de2c11cdf)

Floor4-L3SW

![F4-L3SW](https://github.com/user-attachments/assets/c5aa3167-25f0-46fb-a58e-e82de0dd551a)




### Configuring Core Layer Routers:

Floor1 router

![F1-Router](https://github.com/user-attachments/assets/d80a5b83-ef45-41d1-b16e-4537ec8c3c98)

Floor2 router

![F2-Router](https://github.com/user-attachments/assets/903d0c42-18cb-4ef8-815c-13c83a6f147a)

Floor3 router

![F3-Router](https://github.com/user-attachments/assets/552a966b-3ad8-40a2-8570-966f545a1363)

Floor4 router

![F4-Router](https://github.com/user-attachments/assets/d04e0c79-decd-40f5-bf4a-c0e1fe17be7b)






### Configuring trunk and access ports, VLANS and port security:

Floor1-Management-SW

![sw-mgt](https://github.com/user-attachments/assets/a2b3c49e-0686-45b3-8023-db88aa8964d1)

Floor1-Research-SW

![sw-res](https://github.com/user-attachments/assets/5e56ff1b-86c6-4713-bdbb-e6c998661d94)

Floor1-HR-SW

![sw-HR](https://github.com/user-attachments/assets/a71e2327-e0f7-496e-8f22-594875b0eb22)

Floor2-Marketing-SW

![sw-mkt](https://github.com/user-attachments/assets/2fd45f9c-15ad-43f5-bb89-5e5d85344c8a)

Floor2-Accounting-SW

![sw-Acc](https://github.com/user-attachments/assets/9630d2a0-8147-4803-8a04-1289916300af)

Floor2-Finance-SW

![sw -Fin](https://github.com/user-attachments/assets/a4c0e83f-0902-4411-8c25-23f8bc19f23c)

Floor3-Logistics-SW

![sw-log](https://github.com/user-attachments/assets/b10317e5-a6f1-4289-b52f-af4783a93dfc)

Floor3-Customer-SW

![sw-cust](https://github.com/user-attachments/assets/24c3b6c6-598d-4948-b490-e371e6bfbe5b)

Floor 3-Guest-SW

![sw-guest](https://github.com/user-attachments/assets/36431081-46a1-4819-9a55-985679f7e2e6)

Floor4-Admin-SW

![sw-admin](https://github.com/user-attachments/assets/91626c43-42a3-4dbc-b338-e49658a747bd)

Floor4-IT-SW

![sw-IT](https://github.com/user-attachments/assets/18facbe5-4108-4867-a773-a64b715641d9)

Floor4-Servers-SW

![sw-server](https://github.com/user-attachments/assets/dc4885e3-3fea-493b-8e2c-5f42f07fffae)



### Configuring IP Addresses on Core Layer Routers:

Floor1-Router

![Untitled design (1)](https://github.com/user-attachments/assets/0538784b-f26e-43ac-9aa6-aff63bcc8a81)

Floor2-Router

![Untitled design (2)](https://github.com/user-attachments/assets/001478eb-08ce-45d9-90cc-81e23c2e353c)

Floor3-Router

![Untitled design (3)](https://github.com/user-attachments/assets/93550b4d-7a3b-4f2e-aa75-ad4433874b76)

Floor4-Router

![F4-router](https://github.com/user-attachments/assets/d1ea5cee-99d8-4743-9618-615d87e351b6)


### Configuring inter VLAN routing:

Floor1-L3SW

![F1-L3SW](https://github.com/user-attachments/assets/42a0dfc4-51c3-4276-b724-982d17a3b8e8)

![F1-L3SW 1](https://github.com/user-attachments/assets/b939ca9f-f95d-4b2e-ab8d-0f11616e2c52)

![F1-L3SW 2](https://github.com/user-attachments/assets/2298d447-fccb-4360-b90e-b32939793414)


Floor2-L3SW

![F2-L3SW](https://github.com/user-attachments/assets/c268f0af-0736-4556-ac6b-e5aebba6364b)

![F2-L3SW 1](https://github.com/user-attachments/assets/c7942dd9-1d99-4397-b7f6-bbab387c3d92)

![F2-L3SW 2](https://github.com/user-attachments/assets/eb24703e-2e03-4dc1-815c-00520bec1b2a)


Floor3-L3SW

![F3-L3SW](https://github.com/user-attachments/assets/1413cd54-98c1-401d-a66a-6e039ddd4143)

![F3-L3SW 1](https://github.com/user-attachments/assets/ef2e6ab3-5fb6-454e-b2c5-c4a3cf0fa60c)

![F3-L3SW 2](https://github.com/user-attachments/assets/f39b9aa3-57d8-4eb0-8573-6707d0262ff9)


Floor4-L3SW

![F4-L3SW](https://github.com/user-attachments/assets/604dcfdd-6714-4731-90a1-66408f12acda)

![F4-L3SW 1](https://github.com/user-attachments/assets/ae83a692-4126-4132-bbfe-b6b7424c09ab)

![F4-L3SW 2](https://github.com/user-attachments/assets/189a8ad7-d371-4bb4-bc58-b486a821f231)


Configuring trunk and IP address on layer 3 switches:

Floor1-L3SW

![F1-L3SW](https://github.com/user-attachments/assets/00bb354b-2d3d-42fa-a8bb-76e8be1ae183)

![F1 L3SW](https://github.com/user-attachments/assets/2cb019a4-6256-4a68-94a0-0171f5d2532b)


Floor2-L3SW

![F2-L3SW](https://github.com/user-attachments/assets/d4b83c69-70c1-4aff-84c0-58c9f761c457)

![F2 L3SW](https://github.com/user-attachments/assets/f8410d3f-fde5-482f-abe1-1fb702c8945d)


Floor3-L3SW

![F3-L3SW](https://github.com/user-attachments/assets/b7323498-34df-4fe4-9cd5-268253281ec1)

![F3 L3SW](https://github.com/user-attachments/assets/4eca3503-20a9-4abb-bc2c-5f3fe3cbf0f2)


Floor4-L3SW

![F4-L3SW](https://github.com/user-attachments/assets/781349d4-26ea-45a4-bbcb-5f4a9cdcbf84)

![F4 L3SW](https://github.com/user-attachments/assets/3862bc40-d203-4161-bae6-8282060b0447)



### Configuring OSPF on routers and layer 3 switches:

Floor1-Router

![F1-router](https://github.com/user-attachments/assets/16d36b91-7324-444a-b314-ae753e667a4a)


Floor2-Router

![F2-router](https://github.com/user-attachments/assets/948ee68a-e490-4914-be32-4df2278355eb)


Floor3-Router

![F3-router](https://github.com/user-attachments/assets/db6b7028-1229-4d4f-a4e4-d0b800315cf0)


Floor4-Router

![F4-router](https://github.com/user-attachments/assets/f203da39-d5fa-4562-8756-471216ca4daf)


Floor1-L3SW

![F1 L3SW](https://github.com/user-attachments/assets/dea51b7b-9146-4cb5-81ed-4c1d83ff71df)


Floor2-L3SW

![F2 L3SW](https://github.com/user-attachments/assets/0d86a8cb-1245-4ecb-a066-efd6be56cd72)


Floor3-L3SW

![F3 L3SW](https://github.com/user-attachments/assets/241eb9e6-7318-4c41-89ec-2a15719a3045)


Floor4-L3SW

![F4 L3SW](https://github.com/user-attachments/assets/a5a076f2-f56e-458d-bb43-a655a574fc80)



### Configuring static Ips on servers:

DHCP Server

![dhcp ip](https://github.com/user-attachments/assets/058c0243-2a8b-41b4-960b-89fddbed204d)

Configuring DHCP Server pools:

![dhcp pool](https://github.com/user-attachments/assets/7a03aa8f-c077-4466-9ea5-c9f3777ee413)


WEB Server

![dhcp ip](https://github.com/user-attachments/assets/058c0243-2a8b-41b4-960b-89fddbed204d)

![web](https://github.com/user-attachments/assets/f0c3c34a-346d-47e4-83e9-a2233a43dfe7)


Email Server

![mail ip](https://github.com/user-attachments/assets/838f3dd4-f68f-45e5-a15a-8524eb599a7e)

![email](https://github.com/user-attachments/assets/edf09d52-d766-483d-8165-02488e33523e)



### Checking if DHCP is successful:

Management-PC

![mgt pc](https://github.com/user-attachments/assets/050a38b6-a835-4ac5-9263-768710812d04)


Marketing-PC

![mkt pc](https://github.com/user-attachments/assets/52f989be-f8b2-4612-8e9c-28927696c8b1)


Guest-PC

![guest pc](https://github.com/user-attachments/assets/45902671-de6f-415b-9156-c0512dd6d3c3)


Configuring Access points:

Management-AP

![mgt AP](https://github.com/user-attachments/assets/d61b4347-d906-463a-9d38-14ea486d8838)


Management-Laptop

![mgt laptop](https://github.com/user-attachments/assets/f760e10c-2edb-449a-9b80-db14fcd83e1e)


## Final Network in Packet Tracer

![network](https://github.com/user-attachments/assets/4fb979e5-6f00-42f6-9e3a-e13a66ca6f5e)


