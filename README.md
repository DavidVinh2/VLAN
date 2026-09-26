# VLAN

# Overview

A VLAN is a logical subnet, configured on a switch, that acts as a separate subnet. It helps segment out network for easier administration and added security.

# Procedures

I configured routers, switches, and PC's. I added a switching port to the router. I connected 16 PC'S, 4 of it to their switch using straight-through cables. In addition, I connected the four switches to the router.

<img width="2362" height="1184" alt="VLAN Topology Screenshot" src="https://github.com/user-attachments/assets/6ca6d63e-0d05-41fe-8019-48c7ee15fab4" />

Switching Port Before
<img width="2880" height="1826" alt="Screenshot 2026-09-13 141515" src="https://github.com/user-attachments/assets/2b512174-b2ab-410d-8814-a19eb5288a27" />

Switching Port After
<img width="2880" height="1816" alt="Screenshot 2026-09-13 141537" src="https://github.com/user-attachments/assets/e1a6e4a3-4187-41c4-bdef-d7c28fd57e6c" />



# Network Topology

VLAN 10, Accounting-  192.168.10.0
VLAN 20, Sales-       192.168.20.0
VLAN 30, HR-          192.168.30.0
VLAN 50, IT-          192.168.50.0

# Configurations

# 1. Allocate IP address

I allocated IP address to the hosts from within the subnets they are assigned to:

VLAN 10- 192.168.10.0
VLAN 20- 192.168.20.0
VLAN 30- 192.168.30.0
VLAN 50- 192.168.50.0

I used the following:
* 192.168.10.1, 192.168.10.2, 192.168.10.3, and 192.168.10.4 for VLAN 10
* 192.168.20.1, 192.168.20.2, 192.168.20.3, and 192.168.20.4 for VLAN 20
* 192.168.30.1, 192.168.30.2, 192.168.30.3, and 192.168.30.4 for VLAN 30
* 192.168.50.1, 192.168.50.2, 192.168.50.3, and 192.168.50.4 for VLAN 50


# 2. Configuring Interfaces

I configurated PC's 0-3 with Switch0 into VLAN 10, PC's 4-7 with Switch1 into VLAN 20, PC's 8-11 with Switch2 into VLAN 30, PC's 12-15 with Switch3 into VLAN 50.

<img width="1162" height="522" alt="Screenshot of Interface Configuration" src="https://github.com/user-attachments/assets/6396f660-d2f9-4ef3-9110-8ca981d17970" />


# 3. Checking VLAN on switch

I checked VLAN's on the switch and which ports are in which VLAN's. By default, all ports are in the native VLAN named "default". I used the "show vlan brief" command. 

<img width="1154" height="664" alt="Screenshot 2026-09-14 090438" src="https://github.com/user-attachments/assets/f3a0ea6d-c1cd-4ddb-99bd-d730ad710111" />

# 4. Ping Test

I tested some pings. I should be able to ping between hosts in the same VLAN, but not to the other VLAN.

<img width="1332" height="1308" alt="Screenshot 2026-09-14 092458" src="https://github.com/user-attachments/assets/c08c1b4e-e9d2-445b-b2b7-ded44abd3b13" />
<img width="1342" height="720" alt="Screenshot 2026-09-14 092915" src="https://github.com/user-attachments/assets/85beae56-eba0-47f3-bddc-d5dfa4d7538e" />
<img width="1342" height="720" alt="Screenshot 2026-09-14 092915" src="https://github.com/user-attachments/assets/fbb995f6-cd1d-4832-91ad-f23a2fce2707" />
<img width="1352" height="1232" alt="Screenshot 2026-09-14 093203" src="https://github.com/user-attachments/assets/903bce8d-6bbb-4f9f-9f42-1b250d88314b" />


