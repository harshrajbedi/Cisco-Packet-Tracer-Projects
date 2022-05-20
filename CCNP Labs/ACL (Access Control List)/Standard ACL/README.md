# Standard ACL Lab Senarios

## Senario 1 
We are given with 2 Routers (0 and 1) with switch on each side and some end devices like PC and Server.

**What to Implement**
1. Stop PC1 from reaching Network 192.168.2.0/24
2. Stop PC4 from reaching Network 192.168.1.0/24

- To achieve above requirements we have to first configure the basic connectivity between all devices. I have used static routing because it very easy to implement and also we are just having only 2 Routers so we can proceed with static routing.
- After implementing static routing check connectivity by pinging between either devices.
- Now we will start implmentation of Standard ACL, Steps are as follows
1. Create a number standard ACL and add ACE's to this ACL
2. Implement the above created ACL on correct interface with in or out keyword.
3. Check that is the above condition is satisfied, if not then do some troubleshooting steps

**TOUBLESHOOTING**
- Check Routing is done properly
- Check ACL is configured properly 
- Check that ACL is implemented in required interface
- Check that IP address are assigned properly to the devices
- Check that in or out keyword is suitable in that ACE 
