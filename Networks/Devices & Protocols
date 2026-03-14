Network Devices/Protocols

- MAC Address  
  - 48 bit ‘burned in’ physical id for network hardware  
  - Intended to be permanent  
- Switch  
  - Brain of a LAN  
  - Ensure data sent doesn’t clutter network  
- CAM Table  
  - Switches maintain a CAM table  
  - List that maps device’s physical MAC Address to specific physical port on switch  
- Switch / MAC table Mechanism:  
  - When a packet arrives, the switch looks at the Destination MAC  
  - If the MAC is in CAM table, the data is sent only to that port  
  - If the MAC is unknown, the switch "floods" the data to every port until the correct device responds.  
- ARP (Address Resolution Protocol)  
  - Protocol that links layer 3 (IP addr) and layer 2 (MAC addr)  
  - ARP Process:  
    - Request. Host sends broadcast ‘who has IP x? Tell IP y’  
    - Reply: Device with that IP sends a unicast back ‘I do, my MAC addr is z’  
- ARP Caching  
  - Computers store mapping in ARP cache temporarily  
    (few minutes for thai conversation)  
- Router & IP Routing  
  - IP address  
    - Numerical label assigned to each device  
    - Logical address changes based on network the device is visiting  
    - Unlike MAC which is physical  
    - 32-bit IPV4, 128-bit IPV6  
- IP Components  
  - Network Portion  
    - Identifies specific network or ‘neighborhood’ where device located  
  - Host Portion  
    - Identifies specific device or ‘house’ within that ‘neighborhood’  
- IPV4 Network Layer Packet Structure  
  - Connectionless protocol used on packet-switching networks  
  - No guarantee on delivery or sequence of packets  
  - Note addresses (4 octets each) and Data (service data unit)

| Version | IHL | Type of Service |  | Total Length |  |
| :---: | :---: | :---: | ----- | :---: | :---: |
| Identification |  |  |  | Flags | Fragment Offset |
| TTL |  | Protocol |  | Header Checksum |  |
| Source Address |  |  |  |  |  |
| Destination Address |  |  |  |  |  |
| Options (+ Padding) |  |  |  |  |  |
| Data (Variable) |  |  |  |  |  |

- Subnet Mask  
  - Mathematical ‘filter’  
  - Tells a device where the network portion ends and the host begins  
  - Without a mask, IP addr is a string of numbers without context  
- Subnetting  
  - Computers see IP addresses/masks as 32-bit binary strings  
  - Diving a large network into sub-networks  
    - Smaller, isolated, managable  
  - Subnet mask  
    - Determines boundaries of local network  
    - Act as a block of 1’s. Where the 1’s stop, the network ends and host address begins  
      - Number of devices that can fit in a subnet: 2^n \-2. (n \= host bits)  
        (-2 because first addr is network id, last is broadcast)  
  - Local Traffic  
    - If destination IP shares same network portion as sender, computer knows target is nearby  
    - Sends data through the switch  
  - Remote Traffic  
    - If network portions different, target on a different network  
    - Sends data through the router  
  - CIDR Notation  
    - Classless Inter-Domain Routing  
      - Represents the number of ‘1’ bits in the subnet mask  
      - /24, /16  
      - ex) a /24 mask means the first 24 bits are the network.  
        Leaves 8 bits for hosts. (2^8 \= 256 addresses)  
- Default Gateway  
  - ‘bridge’ between LAN and WAN  
  - IP address of the router interface connected to local subnet  
  - Traffic Forwarding  
    - When a router receives a packet, ignore the MAC address and looks at destination IP  
    - When computer determines destination IP is remote (outside subnet), forwards packet to Default Gateway and trusts router (computer doesn't know the path, relies on router)  
  - Routing Decision  
    - Routing Table  
      - List of known networks and best path to get  
    - Router looks at the packet, checks routing table, decides next hop (another router) or network interface will get packet closer to destination  
  - TTL (Time to Live)  
    - Every time a packet passes a router, TTL val decrease by 1  
    - If 0, drop the packet. Prevent forever loop if network is misconfigured

