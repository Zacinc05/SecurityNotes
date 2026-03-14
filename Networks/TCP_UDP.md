UDP/TCP

- TCP (Transmission Control Protocol)  
  - Connection-oriented and reliable. It ensures every packet arrives correctly and in order via Three-Way Handshake  
  - Connection Establishment  
    - Three Way Handshake  
      - SYN: "can communicate?"  
      - SYN/ACK: "yes, ready"  
      - ACK: "sending data"  
  - Connection Termination  
    - 4-Way Handshake  
      - Machine X sends packet with FLAGS==FIN  
      - Machine Y sends packet with FLAGS==ACK  
      - Machine Y sends packet with FLAGS==FIN  
      - Machine X sends packet with FLAGS==ACK  
  - Source Port  
    - Ports are conceptual locations  
    - Source port is associated with a program on machine sending the packet  
  - Destination Port  
    - Associated with program contacted on the machine receiving the packet  
  - Sequence Number  
    - Identifies which packet is in the sender’s TCP stream  
  - Acknowledgement Number  
    - Sequence number of next packet expected to be received by the sender  
    - Asserts all packets with lower sequence numbers have been received  
  - Data Offset  
    - Size of the TCP header in 32 bit words  
    - Identifies how many options are specified  
  - Flags  
    - Identify any control info communicated by a packet  
    - NS         Nonce Sum: Explicit Congestion Notification (ECN) protection  
    - CWR     Congestion Window Reduced  
    - ECE       ECN Congestion (w/SYN: ECN Capable)  
    - URG      Urgent pointer field is significant  
    - ACK      Acknowledgment field is significant  
    - PSH      Push buffered data to the application  
    - RST      Reset the connection  
    - SYN      Synchronize sequence numbers  
    - FIN        No more data from sender  
  - Checksum  
    - Verifying header and data  
    - Set to 0 to calculate this field  
- UDP (User Datagram Protocol)  
  - Connectionless and fast. It sends data without checking if it arrived  
  - Packet Structure  
    - Like TCP Packets, UDP packets have source and destination port numbers. Aside from this, contain length, checksum and application data

| Source Port Number (16 bit) | Destination Port Number (16 bit) |
| :---: | :---: |
| Length (UDP Header \+ Data) (16 bit) | UDP Checksum (16 bit) |
| Application Data (Message) |  |

