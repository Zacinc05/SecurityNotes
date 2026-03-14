Network

- Collection of devices (nodes) connect to share resources and communicate  
- LAN (Local Area Network)  
  - Restricted network to a small geographic area  
- WAN (Wide Area Network)  
  - Connects multiple LAN’s across great distances  
- Internet  
  - Ultimate example of WAN  
- Host  
  - Any device  
- Client  
  - Device that requests data  
- Server  
  - Device that provides data  
- Node  
  - Connection point

Ports and Services

- 65,535 available ports  
- Port number tells the computer which program (service) should receive that data  
- Well-Known Ports (0-1023)  
  - Reserved for standard system services  
- Registered Ports (1024-49151)  
  - Used by other applications/services  
- Dynamic/Private Ports (49152-65535)  
  - Used temporarily by your computer when you browse the web.

Encapsulation

- Process of every layer adding a header (and sometimes a trailer) to the received unit of data and sending the “encapsulated” unit to the layer below  
- Allows each layer to focus on its intended function  
- Ex)  
  - Application data: It all starts when the user inputs the data they want to send into the application. For example, you write an email or an instant message and hit the send button. The application formats this data and starts sending it according to the application protocol used, using the layer below it, the transport layer.  
  - Transport protocol segment or datagram: The transport layer, such as TCP or UDP, adds the proper header information and creates the TCP segment (or UDP datagram). This segment is sent to the layer below it, the network layer.  
  - Network packet: The network layer, i.e. the Internet layer, adds an IP header to the received TCP segment or UDP datagram. Then, this IP packet is sent to the layer below it, the data link layer.  
  - Data link frame: The Ethernet or WiFi receives the IP packet and adds the proper header and trailer, creating a frame.

