# Azure Virtual Network Lab

## Table of Contents

- [Overview](#overview)
- [Prerequisites](#prerequisites)
- [Creation of Virtual Network]


---

## Overview

This project demonstrates the concepts of azure virtual networking, how to configure virtual network in azure, configure Vnet peering, public and private IP address, intranet in microsoft azure. 
---

## Prerequisites

Before attempting this project, it is recommended to be familiar with:

- Basic networking concepts.
- Knowledge of subnetting.
- Public and private IP address.
- Internet and intranet.

## Creation of Virtual Network
- Creation of virtual network )
<img width="1597" height="663" alt="image" src="https://github.com/user-attachments/assets/3d30ceed-f8ce-447e-a998-a4ec4c70f74d" />

<img width="802" height="820" alt="image" src="https://github.com/user-attachments/assets/dcb67bf0-b81c-45e2-9696-07bb542b5e77" />

(Assign the IP range in vnet-client)
<img width="1006" height="602" alt="image" src="https://github.com/user-attachments/assets/8bc28fea-2589-486d-8e1d-73e3865a2aa3" />

(Add a subnet)
<img width="786" height="354" alt="image" src="https://github.com/user-attachments/assets/d209af01-0e4b-4cab-b3e9-4812891049ac" />

<img width="1106" height="780" alt="image" src="https://github.com/user-attachments/assets/34e80abe-a79b-4869-abad-1e3cd36ba15d" />

(Review and create)
<img width="822" height="753" alt="image" src="https://github.com/user-attachments/assets/9a0bd6cb-8d5d-416c-8537-f60078a44275" />
For another Virtual network, same steps, but we will change the VNET name and the IP range.
- VNET name -> vnet-server
- IP range - > 10.2.0.0/16
- Subnet -> 10.2.0.0/24

(Virtual Network Created)

<img width="1537" height="422" alt="image" src="https://github.com/user-attachments/assets/6d1908eb-caeb-4cbf-b390-e095f081d030" />

## Creation of VM in each subnet.
  1) In vnet-client
     For this lab we will create a windows server as client and then do a remote connection from our host computer via RDP.
  
  <img width="1512" height="748" alt="image" src="https://github.com/user-attachments/assets/f24dee12-0911-41c3-8801-884c08b4c216" />
  (Client VM settings)
  <img width="1086" height="780" alt="image" src="https://github.com/user-attachments/assets/fb30b0cb-a4c5-44c7-b5f2-8d6acf1f4409" />
  (Client VM is ready)
  <img width="1851" height="877" alt="image" src="https://github.com/user-attachments/assets/a44b0e2c-5b51-4786-8d8e-9912b6e429b8" />
  - Now the client virtual machine is ready. We can access it via RDP. Note that you have to allow RDP in order to access it.
  - <img width="1604" height="314" alt="image" src="https://github.com/user-attachments/assets/4f247169-b8d4-4d08-ae22-f37f43bd710d" />
  - <img width="402" height="489" alt="image" src="https://github.com/user-attachments/assets/18e8d5c4-7415-460b-86a5-6cec9cc416d0" />
  - The client is ready, you can check its private IP address from cmd.
    
<img width="1107" height="510" alt="image" src="https://github.com/user-attachments/assets/3d54d3cb-a9cd-47d1-bb74-dbf214d7ed7b" />
Focus on IP address. This IP address falls under the subnet we configured in our vnet-client. Its automatically assign by DHCP.

2) In vnet-server
   For server we will create an ubuntu headless server.
   <img width="956" height="757" alt="image" src="https://github.com/user-attachments/assets/921ea6c1-e18a-48a6-8a40-2b4b320353ed" />
   <img width="853" height="644" alt="image" src="https://github.com/user-attachments/assets/f018e9be-bdba-465d-b894-f3e99853a135" />
   We are setting up in a way that the public IP as none. We will be accessing the server via private IP address. When the deployment is ready, we can see that it doesn't have the public IP address
   <img width="1922" height="872" alt="image" src="https://github.com/user-attachments/assets/e31e4628-4e62-4f9b-8aa2-f4b04be7f16c" />

## Creation of VNET Peering.
Right now the client cannot communicate with server. Meaning we cannot do ssh also. 
<img width="982" height="403" alt="image" src="https://github.com/user-attachments/assets/3b60bd09-7961-4dff-b2ed-8f986e108dc0" />
To do ssh from windows install the OpenSSH Client.
<img width="747" height="787" alt="image" src="https://github.com/user-attachments/assets/3a8ec55a-e407-4245-94d2-2c957590314a" />
No ssh connection
<img width="975" height="526" alt="image" src="https://github.com/user-attachments/assets/23a29865-0c7b-4c65-b3d7-df1b80c9989e" />

## Configure VNET Peerinng
For Peering
<img width="1883" height="848" alt="image" src="https://github.com/user-attachments/assets/e7435674-0f9f-4e59-80bd-9a9e1490af86" />
<img width="912" height="843" alt="image" src="https://github.com/user-attachments/assets/28495c1b-4b9c-4f90-a3b4-9690a56f69e3" />
<img width="1343" height="859" alt="image" src="https://github.com/user-attachments/assets/9fd6f9a2-8353-4383-acc0-deb2fe587883" />

After adding a peering we can talk with our server virtual machine which is in vnet-server.
<img width="983" height="514" alt="image" src="https://github.com/user-attachments/assets/700b12c0-ae0c-466b-b0a5-f727b005e01a" />
SSH connection
<img width="904" height="651" alt="image" src="https://github.com/user-attachments/assets/e54b5731-1ab9-4850-b13f-49941e57ac8e" />

SSH is working fine that means that the VNET peering is working fine.














   
   


   

  

  


   

  
  









