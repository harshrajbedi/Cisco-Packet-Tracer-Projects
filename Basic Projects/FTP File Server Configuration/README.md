# FTP File Transfer Protocol Configuration Project
In this Project a basic FTP connection is established from two different networks and FTP server is configured to work from any device in any network.

## Steps to be followed to configure FTP 
1. Make a network from which FTP server will be accessed. For this we have created two different networks i.e. 192.168.1.0 & 192.168.2.0, I have taken Class C IP address for simple and better understanding although you can use any Class IP address.
2. Attach all the networking devices as your wish.
3. Assign IP addresses, Subnet Mask and Default Gateway to all the devices so that we can communicate with them.
4. After assigning IPs to each interface in the network we have do routing. Routing wll help the data to transfer in efficient way, without routing we cannot communicate to outside the network. I have implemented Dynamic routing or (RIP) means Routing Information Protocol. 
5. After Implementing RIP we are ready to check the communication of our devices inside as well as outside the network.
6. Last step to start configuring the FTP server.


### Configuring the Dynamic Routing.
- Open Router1 > config > Under Routing you will see RIP.
- After entering into RIP you see  network block where you will enter the IP address of a network which is attached with router1.
- Enter all the Networks 1 by 1 by adding them into the RIP list.
- In router1 following Networks are attached 
192.168.1.0, 10.0.0.0, 11.0.0.0
- In router2 following Networks are attached 
100.0.0.0, 12.0.0.0, 11.0.0.0
- In router3 following Networks are attached 
192.168.2.0, 12.0.0.0, 11.0.0.0

### Configuring FTP Server
- Open Server > Config > FTP
- Here you can see we have username and password column where you can add users in this server.
- People only with username and password can access this file server.
- we can give permissions to these users like read, write, delete, rename and list.
- Now our server is finally configured for File Transfer Services.

### Commands used to upload and download files from server
- (***dir***) This command is used to check files available on the server. This can also be used to check files on PC as well.
- (***ftp ip_address***) This command is used to establish a FTP connection between the desired PC let's take example 
PC1 wants to establish a ftp connection with ftp server for file transfer, from this pc a command will run in command prompt as ftp 100.50.20.3
This will try to connect wih the server and then it will ask for username and password that's it.
- (***put file_name_with_extension***) This command will be used when a user want to upload files on the server example,
a user wants to upload a file with name Test1.txt, he will run a command after ftp connection establishment as put Test1.txt, now the file will be uploaded on the server and anyone of the user of that server can access that file.
- (***get file_name_with_extension***) This command will be used when a user want to download files from the server example,
a user wants to download a file with name Test1.txt, he will run a command after ftp connection establishment as get Test1.txt, now the file will be downloaded in his PC.
