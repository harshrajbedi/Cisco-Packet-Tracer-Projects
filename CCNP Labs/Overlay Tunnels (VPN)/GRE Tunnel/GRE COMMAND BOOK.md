# GRE COMMAND BOOK

1. **interface tunnel (tunnel_no)** -> To create a tunnel with a number from 1 to 2147483647.
2. **tunnel source (interface_name)** -> To specify the tunnel source interface.
3. **tunnel destination (ip_address)** -> To specify end point of this tunnel, IP of tunnel's endpoint interface.
4. **ip address (ip_add) (subnet)** -> To give ip address to tunnel interface.
5. **bandwidth (value)** -> To set bandwidth of tunnel from 1 to 10000000 in Kbits/sec
6. **ip mtu (value)** -> 
7. **keepalive (seconds[retries])** -> To specify keepalive timer, default is 10 seconds with 3 retries.
8. **ip mtu (value)** -> To specify MTU size of tunnel interface, default tunnel MTU is 1500-24 = 1476 bytes.
9. **tunnel ttl (0-255)** -> TTL of packet is also encapsulated as part of payload. default value is 255. 