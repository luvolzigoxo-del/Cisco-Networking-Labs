Lab 01 – VLAN Trunking and DHCP
About This Lab

For this lab, I used Cisco Packet Tracer to build a small network with a router, two switches and a few PCs.

I wanted to practise VLANs, trunking, inter-VLAN routing and DHCP instead of only reading about them.

I used two VLANs:

VLAN 10 – SALES
VLAN 20 – IT

The idea was to keep the two departments on separate networks, but still allow them to communicate through the router.

NETWORK TOPOLOGY

<img width="802" height="542" alt="image" src="https://github.com/user-attachments/assets/5ea65a3e-7b20-4880-acf5-311d5eef2b06" />

The lab includes:

R1 – Router
SW1 – Main switch
SW2 – Second switch
PCs for the different VLANs
VLAN 10 – SALES
VLAN 20 – IT

What I configured
VLANs

I created VLAN 10 and VLAN 20 on the switches and assigned the PC ports to the correct VLAN.
I then checked the configuration with:

show vlan brief
This helped me confirm that the VLANs were created and that the ports were assigned correctly.

Trunking
I configured the link between the switches as a trunk.

I used:

show interfaces trunk

to check that the trunk was working.
This was useful for understanding how traffic from more than one VLAN can travel between switches using the same link.


Inter-VLAN routing

I configured R1 to handle the two VLAN networks.
This allowed the devices in SALES and IT to communicate with each other.
I checked the router interfaces using:
show ip interface brief

DHCP

I also configured DHCP on R1.
The reason for doing this was to let the PCs get their IP addresses automatically instead of configuring each PC manually.
I checked the DHCP leases using:

show ip dhcp binding

TESTING

Once I had finished the configuration, I tested the network from the PCs.
I used ping to check whether the PCs could communicate across the different VLANs.
I also used tracert to see the path the traffic was taking.
These tests helped me confirm that the router was being used to move traffic between the VLANs.

SCREENSHOTS

Topology
<img width="1595" height="576" alt="image" src="https://github.com/user-attachments/assets/0259403b-887d-460d-b865-28b52c890554" />

Configs

SW1 Configs

[SW1 configs.txt](https://github.com/user-attachments/files/32979328/SW1.configs.txt)

SW2 Configs

[SW2 config.txt](https://github.com/user-attachments/files/32979382/SW2.config.txt)


R1 Configs

[R1# configs.txt](https://github.com/user-attachments/files/32979394/R1.configs.txt)

SCREENSHOTS

Show ip dhcp binding R1

<img width="636" height="85" alt="show ip dhcp binding " src="https://github.com/user-attachments/assets/bb81c8b7-d05e-4e17-ad46-8374f8953688" />

Show ip interface brief R1

<img width="633" height="143" alt="show ip interface brief" src="https://github.com/user-attachments/assets/e0ba4d39-091a-4a34-b173-ebd53c20d103" />

Show ip intefaces trunk

<img width="640" height="250" alt="SW1 - show interfaces trunk" src="https://github.com/user-attachments/assets/b5baf8d4-dd1a-4d53-a824-47b3a2e6a2dc" />

SW1 Vlan Brief


<img width="637" height="280" alt="SW1 - show vlan brief" src="https://github.com/user-attachments/assets/65580e87-87ef-4242-b841-f32e1a19fb4a" />

SW2 Vlan Brief


<img width="630" height="461" alt="image" src="https://github.com/user-attachments/assets/c6950ff7-90bc-46db-9d3e-cb8d51b2c36a" />

Ping Test PC1



<img width="703" height="713" alt="image" src="https://github.com/user-attachments/assets/c103dcf2-af24-4df0-b451-c04521fc88c0" />

Traceroute



<img width="657" height="153" alt="tracert 192 168 20 11" src="https://github.com/user-attachments/assets/5812c16e-7cf2-436c-ad86-fdb3bdd21276" />



Troubleshooting

While doing the lab, I used the show commands to check different parts of the configuration.

The main commands I used were:

show vlan brief
show interfaces trunk
show ip interface brief
show ip dhcp binding

If something wasn't working, I checked the network one part at a time.

For example, I checked the VLANs first, then the trunk, then the router interfaces and DHCP.

I also used ping to test connectivity.

This helped me get into the habit of checking the actual configuration instead of just changing commands and hoping the problem goes away.

Result

The lab worked and I was able to get the PCs to receive their IP addresses through DHCP.
I initially had an issue with the trunk and had to go back and check the VLAN configuration.
I was also able to test communication between the different VLANs.

There were a few things I had to check along the way, but working through them helped me understand the setup better.




