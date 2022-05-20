# GRE Tunnel Short Notes

## What is GRE Tunnel
- It is a ***Generic Routing Encapsulation Tunnel*** is a protocol for encapsulating data packets that use one routing protocol inside the packets of another protocol.
- It is usually configured between routers. Each router acts like one end of the tunnel.
- End routers send and receive GRE packets directly to each other.
- GRE forms Point 2 Point (P2P) tunnel.
- Any router in between the tunnel will not open encapsulated packet, only the headers outside will be used to forward the packets.

## About GRE Header
- Packets have 2 parts **PAYLOAD** Means actuall data to send and **HEADER** Means where it come from and what protocols are attached.
- GRE attaches 2 headers to the packet - **the GRE header (4 bytes)** it indicates the protocol type used by encapsulated packet and **ip header (20 bytes)** it encapsulates the original packet's header and payload. This means that GRE packet usually has two IP headers: one for original packet and one for added by GRE protocol.
- GRE header allows packet to route through tunnel to the destination without inspection of payload.

## Some Important points to remember 
1. Private Networks uses RFC1918 Address Space, as they are non routable address. To create VPN between private networks we use GRE Tunnel (tunneling overlay technology)
2. Recursive routing and outbound interface selection are two common problems with tunnel or overlay networks.