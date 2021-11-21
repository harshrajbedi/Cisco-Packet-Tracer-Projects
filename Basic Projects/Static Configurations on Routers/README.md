# Static Configuration on Router 
In this project we are configuring static routes between 2 different networks. 

## EXPLAINING THE PROJECT


### STEPS TO BE FOLLOWED IN THE CONFIGURATION
1. Collect 4 End devices, 2 Switches and 2 Routers
2. Divide end devices into 2 networks including 1 switch at each side
3. Connect both switches to individual routers 
4. Cables used between end devices, switch-router is copper straight-through cable.
5. Cables used between Routers is Cross over cable
6. Finally we build the topology and now we have to configure individual devices so that they can communicate with each other. 

#### CONFIGURING EACH DEVICE
Configuring End Devices - PCs 
1. To configure PCs click on PC, go to Config tab.
2. Enter default gateway address in Gateway/DNS IPv4 section.
3. Now go to FastEthernet0 section under Interface on left side panel.
4. Here we enter IPv4 address and Subnet Mask under IP configuration.
5. Repeat these steps in other PCs.

Configuring Switches
We do not need to configure switch as we are just connecting end devices together. we are not implementing any switch feature here like VLANS.

***Configuring Router0***
1. Open CLI on router.
2. We assign IPv4 address on both of the interfaces of router0.
3. Below is the command list used to configure router in CLI.
4. After assigning IPv4 address, we add static routes.
5. In CLI enter command ip route (ip_add of destination network) (subnet_mask) (next_router/hop ip_add)
This command will look like --
ip route 192.168.5.0 255.255.255.0 192.168.100.2

***Configuring Router1***
1. Do same steps until Ipv4 assignment on both interface like in router0.
2. In CLI enter command ip route (ip_add of destination network) (subnet_mask) (next_router/hop ip_add)
This command will look like --
ip route 192.168.1.0 255.255.255.0 192.168.100.1

##### TESTING PHASE OF THIS PROJECT 
Here we test the configuration we did on all the devices.
Ping test in conducted from PC0 to PC2 i.e. ping from network 1 to network 2
We successfully ping with 0% loss.

##### COMMANDS USED IN THIS CONFIGURATION
en - used to enable the CLI mode
conf t - used to enter the configuration mode
int (interface_name) - example [int fa0/1] used to enter into a specific interface
ip address (ip_add) (subnet_mask) - used to assign ip to a interface
show ip int brief - to show ip addresses on all the interfaces
show ip route - to show all the ip routes on this router
