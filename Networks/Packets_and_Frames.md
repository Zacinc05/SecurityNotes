Packet

- Piece of data containing info such as an IP header and payload  
- Efficient way to communicate data across network devices  
- Layer 3 (Network Layer) on OSI model

Frame

- Encapsulates the packet and adds info such as MAC addresses  
- Layer 2 (Data Link) on OSI model

Header (more info in Exploitation/Headers file)

- Time to Live  
  - Set expiry timer for the packet to not clog up your network  
- Checksum  
  - If any data is changed, this value will be different from what was expected and will corrupt  
- Source Address  
  - The IP address of the device that the packet is being sent from so that data knows where to return to.  
- Destination Address  
  - The device's IP address the packet is being sent to so that data knows where to travel next.

Encapsulation

- Process of every layer adding a header (and sometimes a trailer) to the received unit of data and sending the “encapsulated” unit to the layer below  
- Allows each layer to focus on its intended function  
- Ex)  
  - Application data: It all starts when the user inputs the data they want to send into the application. For example, you write an email or an instant message and hit the send button. The application formats this data and starts sending it according to the application protocol used, using the layer below it, the transport layer.  
  - Transport protocol segment or datagram: The transport layer, such as TCP or UDP, adds the proper header information and creates the TCP segment (or UDP datagram). This segment is sent to the layer below it, the network layer.  
  - Network packet: The network layer, i.e. the Internet layer, adds an IP header to the received TCP segment or UDP datagram. Then, this IP packet is sent to the layer below it, the data link layer.  
  - Data link frame: The Ethernet or WiFi receives the IP packet and adds the proper header and trailer, creating a frame.
