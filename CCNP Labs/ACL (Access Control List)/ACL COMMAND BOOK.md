# ACL COMMAND BOOK

## Standard ACL
1. **access-list (acl_number) {deny|permit}** -> To define ACL                                 
2. **ip access-group (acl-number) {in|out}** -> To apply ACL on interface                     

## Extended ACL

3. **access-list acl-number {deny|permit} protocol source source-wildcard destination destination-wildcard[protocol-options] [log|log-input]** -> To define Extended ACL using source and destination address, protocol, port number and using log to get log messages in command line when that particular entry hits or matches.
4. **ip access-group (acl-number) {in|out}** -> To apply ACL on interface

## Named ACL
5. **ip access-list {standard|extended} {acl_number|acl_name}** -> To create named ACL

## Port ACL
It uses 3 keywords lt - less than, gt - greater than and eq - equivalent
### Example of PACL
1. deny tcp any any eq 23

## Basic ACL Commands
6. **show access-lists** -> To see defined ACLs
7. **no access-list (acl_number)** -> To delete ACL group (like 100 or 110)
8. **ip access-list {standard|extended} (acl_number)** -> To Edit Numbered ACL (ACL Configuration Mode)
9. **no (acl_sequence_number)** -> To delete a ACE from ACL
10. **exit** -> To exit ACL configuration mode
11. **(sequence_number) {deny|permit} ...** -> To create a new ACE (location of ACE depends upon sequence number)
12. **access-list 1 permit any** -> To create ACE that permits any IP
