# VLAN

# Overview

A VLAN is a logical subnet, configured on a switch, that acts as a separate subnet. It helps segment out network for easier administration and added security.

# Procedures

I configured routers, switches, and PC's. I added a switching port to the router. I connected 16 PC'S, 4 of it to their switch using straight-through cables. In addition, I connected the four switches to the router.

<img width="2362" height="1184" alt="VLAN Topology Screenshot" src="https://github.com/user-attachments/assets/cdede484-7dec-4272-b847-f5c96d089d4b" />

Switching Port Before
<img width="2880" height="1826" alt="Screenshot 2026-09-13 141515" src="https://github.com/user-attachments/assets/2b512174-b2ab-410d-8814-a19eb5288a27" />

Switching Port After
<img width="2880" height="1816" alt="Screenshot 2026-09-13 141537" src="https://github.com/user-attachments/assets/e1a6e4a3-4187-41c4-bdef-d7c28fd57e6c" />



# Network Topology

VLAN 10, Accounting-  192.168.10.0
VLAN 20, Sales-       192.168.20.0
VLAN 30, HR-          192.168.30.0
VLAN 40, IT-          192.168.40.0

# Configurations

# 1. Allocate IP address

I allocated IP address to the hosts from within the subnets they are assigned to:

VLAN 10- 192.168.10.0
VLAN 20- 192.168.20.0
VLAN 30- 192.168.30.0
VLAN 40- 192.168.40.0

I used the following:
* 192.168.10.1, 192.168.10.2, 192.168.10.3, and 192.168.10.4 for VLAN 10
* 192.168.20.1, 192.168.20.2, 192.168.20.3, and 192.168.20.4 for VLAN 20
* 192.168.30.1, 192.168.30.2, 192.168.30.3, and 192.168.30.4 for VLAN 30
* 192.168.40.1, 192.168.40.2, 192.168.40.3, and 192.168.40.4 for VLAN 40

<img width="1200" height="682" alt="Scrrenshot of VLAN Data Entry" src="https://github.com/user-attachments/assets/b097e2e0-096f-44e2-af92-c50e54cfbcfc" />



# 2. Configuring Interfaces

I configurated PC's 0-3 with Switch0 into VLAN 10, PC's 4-7 with Switch1 into VLAN 20, PC's 8-11 with Switch2 into VLAN 30, PC's 12-15 with Switch3 into VLAN 40.

<img width="1162" height="522" alt="Screenshot of Interface Configuration" src="https://github.com/user-attachments/assets/6396f660-d2f9-4ef3-9110-8ca981d17970" />


# 3. Checking VLAN on switch

I checked VLAN's on the switch and which ports are in which VLAN's. By default, all ports are in the native VLAN named "default". I used the "show vlan brief" command. 

<img width="1154" height="664" alt="Screenshot 2026-09-14 090438" src="https://github.com/user-attachments/assets/f3a0ea6d-c1cd-4ddb-99bd-d730ad710111" />
<img width="1172" height="662" alt="Screenshot 2026-09-14 090654" src="https://github.com/user-attachments/assets/97a57fbf-9b07-401d-b68e-77d9c44c111b" />
<img width="1178" height="676" alt="Screenshot 2026-09-14 090928" src="https://github.com/user-attachments/assets/8b71a05c-f0ee-4c5e-a4a7-d1a9d43a6138" />



# 4. Ping Test

I tested some pings. I should be able to ping between hosts in the same VLAN, but not to the other VLAN.

<img width="1332" height="1308" alt="Screenshot 2026-09-14 092458" src="https://github.com/user-attachments/assets/c08c1b4e-e9d2-445b-b2b7-ded44abd3b13" />
<img width="1342" height="720" alt="Screenshot 2026-09-14 092915" src="https://github.com/user-attachments/assets/85beae56-eba0-47f3-bddc-d5dfa4d7538e" />
<img width="1342" height="720" alt="Screenshot 2026-09-14 092915" src="https://github.com/user-attachments/assets/fbb995f6-cd1d-4832-91ad-f23a2fce2707" />
<img width="1352" height="1232" alt="Screenshot 2026-09-14 093203" src="https://github.com/user-attachments/assets/903bce8d-6bbb-4f9f-9f42-1b250d88314b" />


# 5. VLAN Review

I noticed that Fa0/4 in each individual switches are in default instead of being in their VLAN for VLAN's 10, 20, 30, & 40. Therefore, I made changes by configuring Fa0/4 for individual switches for VLAN's 10, 20, 30, & 40. After pinging the four PC's (PC's 3, 7, 11, &, 15), I noticed that all 16 PC's are connected to their VLAN's and they have a successful connection. 
<img width="1150" height="720" alt="Screenshot of full VLAN 10 configuration" src="https://github.com/user-attachments/assets/d9622d75-6923-4504-a3d2-d638e96a1ebb" />
<img width="1286" height="798" alt="Screenshot of full VLAN 20 configuration" src="https://github.com/user-attachments/assets/370f39e6-835b-4f0e-b2ea-71cdbcc350eb" />
<img width="1224" height="724" alt="Screenshot of full VLAN 30 configuration" src="https://github.com/user-attachments/assets/7ff21d42-8125-40df-b666-c964f3eac290" />
<img width="1348" height="712" alt="Screenshot of full VLAN 40 configuration" src="https://github.com/user-attachments/assets/0981f1b8-9688-42a2-8ee8-96a67d4d3a01" />
<img width="2880" height="1308" alt="Screenshot of ping to 192 168 10 4" src="https://github.com/user-attachments/assets/0eac349e-d01c-42f5-a718-158ac0b112d6" />
<img width="2862" height="1394" alt="image" src="https://github.com/user-attachments/assets/df0864c5-7788-4461-9796-e6184a8a4c8b" />
<img width="2866" height="1332" alt="image" src="https://github.com/user-attachments/assets/30a82315-10ed-49f6-a14f-761a6cd15d49" />
<img width="2880" height="1334" alt="image" src="https://github.com/user-attachments/assets/d234855b-8da8-45dd-abcf-39187667a8c6" />

# Conclusion

This project help me understand how VLAN's are used to logically separate network for easier administration and added security. 






