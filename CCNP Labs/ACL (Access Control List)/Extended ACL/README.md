# Extended ACL Lab Scenarios

## Scenario 1 
There are many network devices in this scenario including routers and switches.

### Objectives
1. Block 192.168.2.2 from communicating with HTTP server in network 192.168.1.0/24.
2. Block 192.168.1.2 from sending ICMP packets to server0.

- To achieve above requirements we have to first configure the basic connectivity between all devices. I have used static routing because it very easy to implement and also we are just having only 2 Routers so we can proceed with static routing.
- After implementing static routing check connectivity by pinging between either devices.
- Now we will start implmentation of Extended ACL, Steps are as follows
1. Create a extended numbered ACL and add required ACE's to this ACL.
2. Implement the above created ACL on correct interface with in or out keyword.
3. Check that objectives are satisfied, if not then do some troubleshooting steps

**TROUBLESHOOTING**
- Check Routing is done properly
- Check ACL is configured properly 
- Check that ACL is implemented in required interface
- Check that IP address are assigned properly to the devices
- Check that in or out keyword is suitable for that interface 

## Scenario 2
This scenario is somewhat realistic and more knowledgable than the previous one, as there are 4 routers and real life example of company network is added. HQ - is Headquater of a company named xyz and BR - is Branch of that xyz company located somewhere far from HQ.

### Objectives
1. Stop Connectivity from Branch to Headquater's FTP Server.
2. Stop Connectivity from Headquater to Branch's FTP Server.

- I have implemented OSPF between router's and there all the connectivity is up, there is only need for Extended ACL to hit our objectives.
- Extended ACL's steps are as follows
1. Create Extended ACL and add deny and permit ACE's accordingly
2. Add these ACL's to suitable position in the network so that other connectivity should not be interrupted.
3. Check that objectives satisfied, if not then do some troubleshooting steps

**TROUBLESHOOTING**
- Check Routing is done properly
- Check ACL is configured properly 
- Check that ACL is implemented on required interface
- Check that IP address are assigned properly to the devices
- Check that in or out keyword is suitable for that interface 
