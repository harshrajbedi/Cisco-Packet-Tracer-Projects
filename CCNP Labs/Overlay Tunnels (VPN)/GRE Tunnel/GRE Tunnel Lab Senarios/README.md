# GRE Tunnel Lab Senarios

## Senario 1 
We are given with 2 Routers (0 and 1) with switch on each side and some end devices like PC and Server.

**Objectives**

Create a tunnel from Router1 to Router2, having an IP address of 192.168.100.0/24 of tunnel.

- To achieve above requirements we have to first configure the basic connectivity between all devices. I have used static routing because it very easy to implement and also we are just having only 2 Routers so we can proceed with static routing.
- After implementing static routing check connectivity by pinging between either devices.
- Now we will start implmentation of GRE Tunnel, Steps are as follows
1. Create a tunnel interface and give it a number from 1 to 2147483647.
2. Give tunnel source interface and destination IP address.
3. Give IP address to tunnel's interface , if not then do some troubleshooting steps

**TOUBLESHOOTING**
- Check Routing is done properly
- Check GRE is configured properly 
- Check that Source interface and Destination IP is configured properly
- Check that IP address are assigned properly to the devices 
