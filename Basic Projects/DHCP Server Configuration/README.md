# DHCP Server Configuration Project
In this project a DHCP Server is configured, it is a type of server which allows us to assign IP addresses to different devices automatically from a given pool of IPs.

## Steps to be followed to configure DHCP Server
1. Make a network to which DHCP Server will assign the IPs. For this Project i have taken 9 PCs, Switch and a Server.
2. Make a connection between all these networking devices with help of physical wires.
3. Now start configuring the DHCP Server.

### Configuring the DHCP Server.
1. DHCP Server > Services > DHCP. Now we have to choose the IP Range for this server, let's take Network ID 192.168.1.0

Now here are some IPs to be followed - 
Network ID - 192.168.1.0,
Default Gateway - 192.168.1.1,
Subnet Mask - 255.255.255.0,
IP Address Range - 192.168.1.0 - 192.168.1.255,
Usable IP Address Range - 192.168.1.1 - 192.168.1.254,
Total Hosts - 256,
Usable Hosts - 254

2. Now we have gathered all the Information required to configure DHCP Server. So follow the steps
- In DHCP Tab you will find Pool Name, enter the desired pool name
- Next is Default Gateway, fill 192.168.1.1
- Next is DNS Server, it is IP of server itself 192.168.1.1, here default gateway and server's IP are same.
- Next is starting IP address, fill 192.168.1.2
- Next is Subnet Mask, fill 255.255.255.0 which is default subnet mask of Class C IP
- Next is Maximum users, fill by your requirements, example 32
- Click on add to add this IP range into the Server's IP Pool.

### Testing the DHCP Server 
- To test the working of DHCP Server goto each PCs config > interface (Fastethernet0) and change Static option to DHCP in IP Configuration block.
- Now DHCP will automatically pick vacant IP address and allocate it the corresponding PC or any network device which takes up IP.



