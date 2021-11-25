# Default Routing and Static Routing Combination to Access Internet.
In this project situation is taken as there is headquater for company in Mumbai and there are many users using end devices. Company opens a new branch in Delhi. As it is a small branch of the company so we want to make sure that configuring network in branch office should be less as much. Task is to configure Branch and Headquater network and connect Branch office and Headquater to the Internet i.e. ISP center.

## EXPLAINING THE PROJECT
First we will make and configure headquater network and then connect this headquater to internet (ISP). Then after configuring HQ, we then configure Branch Office (Make sure that branch office can communicate with headquater and can access internet). 
Concept of Routing (Static and Default) will be used.

### STEPS TO BE FOLLOWED IN THE CONFIGURATION
1. Collect 6 End devices, 2 Switches and 3 Routers
2. Divide end devices into 2 networks including 1 switch at each side
3. Connect both switches to individual router
4. Connect Headquater router to ISP router 
4. Cables used between end devices, switch-router is copper straight-through cable.
5. Cables used between Routers is serial cable
6. Finally we build the topology and now we have to configure individual devices so that they can communicate with each other.

#### CONFIGURING EACH DEVICE
Configuring End Devices - PCs 
1. To configure PCs click on PC, go to Config tab.
2. Enter default gateway address in Gateway/DNS IPv4 section.
3. Now go to FastEthernet0 section under Interface on left side panel.
4. Here we enter IPv4 address and Subnet Mask under IP configuration.
5. Repeat these steps in other PCs.

> Configuring Switches

We do not need to configure switch as we are just connecting end devices together.

We are not implementing any switch feature here like VLANS.

> Configuring Router (HQ-MUMBAI)
1. Open CLI on router.
2. We assign IPv4 address on both of the interfaces of router (HQ-MUMBAI).
At interface se0/0 - 192.168.1.2/24
At interface se0/1 - 1.1.1.1/8
3. Below is the command list used to configure router in CLI.
4. After assigning IPv4 address, we add static route and default route.
5. In CLI enter command `ip route (ip_add of destination network) (subnet_mask) (next_router/hop ip_add)`
This command will look like --
ip route 192.168.2.0 255.255.255.0 192.168.1.1
6. Now we configure static route in this router to redirect any traffic to internet i.e. ISP router so that headquater can have internet access.
To add default route we use 0.0.0.0 as network and 0.0.0.0 as subnet mask, last address will be ISP router 
`ip route 0.0.0.0 0.0.0.0 1.1.1.1`

> Configuring Router (BR-DELHI)
1. Do same steps until Ipv4 assignment on both interface like in router (HQ-MUMBAI).
2. Interface fa0/0 - 192.168.2.1/24
Interface se0/0 - 192.168.1.1/24
2. Add Static route to send traffic to HQ router In CLI enter command ip route (ip_add of destination network) (subnet_mask) (next_router/hop ip_add)
This command will look like --
ip route 192.168.3.0 255.255.255.0 192.168.1.2
4. Here we will not add any default route as we just want to send traffic only to HeadQuater router after reaching HQ router, due to default route on HQ router it will redirect traffic to ISP if it is meant for...

##### TESTING PHASE OF THIS PROJECT 
Here we test the configuration we did on all the devices.

Ping test in conducted from Laptop0 to Laptop5 i.e. ping from network 1 to network 2

We successfully ping with 0% loss.

All the traffic is going to and from HQ and BR router.


##### COMMANDS AND NETWORKS USED IN THIS CONFIGURATION
COMMANDS - 

`en` - used to enable the CLI mode

`conf t` - used to enter the configuration mode

`hostname (host_name)` - To set a hostname for router

`int (interface_name)` - example [int fa0/1] used to enter into a specific interface

`ip address (ip_add) (subnet_mask)` - used to assign ip to a interface

`ip route (ip_add) (subnet_mask) (next_hop)` - To add static ip route

`show ip int brief` - to show ip addresses on all the interfaces

`show ip route` - to show all the ip routes on this router

NETWORKS - 
192.168.1.0 Between Branch router and Headquater router.

192.168.2.0 @ Branch Office.

192.168.3.0 @ Headquater Office.

1.1.1.0 Between Headquater Office and ISP.

##### TO ACCESS THE INTERNET
To access internet we have to implement NAT (Network Address Translation) which will convert private ip to public ip (which is routable).

Commands to Implement NAT are -

`HQ-Mum(config)#access-list 1 permit 192.168.2.0 0.0.0.255`

`HQ-Mum(config)#access-list 1 permit 192.168.3.0 0.0.0.255`

`HQ-Mum(config)#ip nat inside source list 1 interface se0/1 overload` 

`HQ-Mum(config)#int se0/1`

`HQ-Mum(config-if)#ip nat outside`

`HQ-Mum(config-if)#int fa0/0`

`HQ-Mum(config-if)#ip nat inside`

`HQ-Mum(config-if)#int se0/0`

`HQ-Mum(config-if)#ip nat inside`
