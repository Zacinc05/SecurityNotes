ICMP (Internet Control Message Protocol)

- For network diagnostics, error reporting, and control messages in IP networks  
- Core Mechanisms  
  - Echo Request/Reply (Ping)  
    - host sends an "Echo Request" to IP. If the IP is active and configured to respond, it sends back an "Echo Reply." Confirms the host is "alive"  
  - Time Exceeded  
    - If a packet’s TTL hits zero before reaching its destination, a router sends this ICMP message back to the sender. Important for Traceroute  
  - Destination Unreachable  
    - Sent by a router or host when a requested destination or port cannot be reached (i.e. closed port or a downed link)  
- Common ICMP Packet Types  
  - 0 \= Echo reply,	3 \= Dest unreachable,		5 \= Redirect,  
    8 \= Echo request,	11 \= TTL exceeded  
- ICMP Packet Payload Structure  
  - Message Type: 8 bits  
  - Code (subtype of message): 8 bits  
  - Checksum (of header \+ data excluding checksum): 16 bits  
  - Other header data (labeled Quench here): 32 bits  
  - Data \- rest of packet

