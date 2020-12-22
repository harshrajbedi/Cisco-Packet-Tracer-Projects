# Project 1 In Detail

### Networking Devices Used
1. Switch
2. Router

Explaination
------------
Router_1 is connected to Switch_1. 
Switch_1 is connected to Switch_2. 
Switch_2 is connected to Router_2. 

Interfaces:- This gives us the ports where cables are connected.
| Devices              | Interface     |   
| -------------------- |:-------------:|  
| Router_1 to Switch_1 | fa0/0 & fa0/2 |   
| Switch_1 to Switch_2 | fa0/1 & fa0/1 | 
| Switch_2 to Router_2 | fa0/2 & fa0/0 |

IP Address assigned to Router_1 is 10.0.0.1 with a subnet mask of 255.255.255.240
IP Address assigned to Router_2 is 10.0.0.3 with a subnet mask of 255.255.255.240

| Vlans  | Port No. |
| ------:| --------:|
| Vlan10 | fa0/2    |

Connectivity checked in this topology by Ping Command 
Ping router_2 from router_1 with a success rate of 100%

#### Commands Used

|            Commands            | 
| ------------------------------ | 
|             enable             |
|            hostname            |
|            config t            |
|          vlan vlan_no          |
|     switchport mode access     |
| switchport access vlan vlan_no |
| ip address ip_add subnet_mask  |
