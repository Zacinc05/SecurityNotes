https://tryhackme.com/room/networkingessentials

ARP (Address Resolution Protocol)

- Allow devices to identify themselves on a network  
- Associate MAC address with an IP address  
- Store the information via cache  
- ARP sends messages to map identifiers  
  - ARP Request  
    - Broadcast “What is the MAC address that owns this IP address”  
  - ARP Reply  
    - Send MAC address if have corresponding IP addr

DHCP (Dynamic Host Configuration Protocol)

- Automatic configuration of IP address  
  - DHCP Discover  
    - Device connects and doesn't have an IP, requests one to DHCP server  
  - DHCP Offer  
    - Offer an IP addr the device could use  
  - DHCP Request  
    - Device confirms it wants the offered IP Address  
  - DHCP ACK  
    - DHCP server acknowledges the device and its IP addr  
- Transmission Details  
  - Client without an IP sends packets from the IP address 0.0.0.0 to the broadcast IP address 255.255.255.255  
  - Client sends to the broadcast MAC address, ff:ff:ff:ff:ff:ff
