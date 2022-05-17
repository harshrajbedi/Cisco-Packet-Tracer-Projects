# Access Control List Short Notes

## Use of ACL
- NAT, QoS, Class-map, route-map and Packet Filtering 

in - inbound ACL
out - outbound ACL

## Types of ACLs
1. Standard ACL
- Normal Range - 1-99
- Expanded Range 1300-1999 
- Non Editable
- Always apply near destination
- Only checks Source IP Address

2. Extended ACL
- Normal Range - 100-199
- Expanded Range - 2000-2699
- Editable using Named ACL
- Always apply near source
- Checks Source IP, Destination IP, Ports and Combination of other protocols attributes

3. Named ACL (NACL)
- Similar to Standard and Extended but uses names instead of numbers.

4. Port ACL (PACL)
- It uses standard, extended, named, and named extended MAC ACLs To filter layer 2 switchports
- It supports layer 2 MAC Address filtering
### But it has some Restrictions
- Only support incoming traffic.
- Connot filter layer 2 control packet such as CDP, VTP, DTP, PAgP, UDLD,and STP.
- It is supported only in hardware
- Do not support ACLs to filter IPv6, ARP or MPLS traffic.

5. VLAN ACL (VACL)
- It uses standard, extended, named, and named extended MAC ACLs To filter traffic on VLANs.

## ACE (Access Control Entries)
These are the set of rules created inside ACL in a sequential order.
For Example - A Standard ACL numbered 10 is created and it defines ACE inside as - 
10 deny host 192.168.1.2
20 permit any

10 and 20 are sequence number and these statements are called ACE.

### ACE are matched in top to bottom, 10 will be matched first and then 20 will be matched.
### There is a deny ACE underneath of the above ACEs. So if we have to deny every user and permit some users then we can only write permit ACE and router will automatically deny other users. So there is a default deny ACE in every empty as well as filled ACL with ACEs. 

## Modifying ACLs
We can modify ACLs as per our requirements 
To edit ACL use - ip access-list standard|extended (number)
Then it will enter into ACL configuration mode - (config-std-nacl)#










