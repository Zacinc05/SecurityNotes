OSI Model

- Open Systems Interconnection  
- Conceptual framework to understand how data moves from physical wire to user application  
- 7 layers  
  - Physical  
    - Actual hardware  
    - Physical data transmission media  
  - Data Link  
    - Local delivery (switches, MAC address, ARP)  
    - Reliable data transfer between adjacent nodes  
  - Network  
    - Routing across networks (IP addr, router, ICMP)  
    - Logical addressing and routing between networks  
  - Transport  
    - End to end communication (TCP, UDP, Ports)  
    - End-to-end communication and data segmentation  
  - Session  
    - Manage connections between applications  
    - Establishing, maintaining, and synchronising sessions  
  - Presentation  
    - Data format and Encryption (SSL/TLS. JPG, ASCII)  
    - Data encoding, encryption, and compression  
  - Application  
    - User interact with (HTTP, SSH, DNS)  
    - Providing services and interfaces to applications  
- SDU (Service Data Units)  
- PDU (Protocol Data Units)

Encapsulation

- Pieces of information get added to data

OSI component examples

- Application  
  - Protocols and rules are in place to determine how the user should interact with data sent or received  
  - Graphical User Interface (GUI) for users to interact with data sent or received.  
  - DNS (Domain Name System) is how website addresses are translated into IP addr  
- Presentation  
  - Standardisation starts to take place  
  - Translator for data to and from the application layer  
  - HTTPS and other data encryption  
- Session  
  - Create and maintain the connection to other computer for which the data is destined  
  - Checkpoints for if data is lost (save bandwidth on resend)  
  - When a connection is established, a session is created.  
    - While this connection is active, so is the session  
- Transport  
  - Transmitting data across a network  
    - TCP (Transmission Control Protocol)  
    - UDP (User Datagram Protocol)  
- Network  
  - Routing & re-assembly of data (dealing w/ IP address)  
  - OSPF (Open Shortest Path First)  
  - RIP (Routing Information Protocol)  
  - Decide what route is taken  
- Data Link  
  - Adds in the physical MAC (Media Access Control) address of the receiving endpoint  
- Physical  
  - Ethernet cables connecting devices
