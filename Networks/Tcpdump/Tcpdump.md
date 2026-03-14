Basic info/history

- Libpcap  
- Ported to MS Windows as winpcap

Specify the Network Interface

- \-i INTERFACE (for specific interface)  
- \-i any (for all)  
- Use ‘ip a s’ to find interfaces

Save the Captured Packets

- \-w FILE (save to a file)  
- Most commonly a ‘.pcap’ file

Read Captured Packets from a File

- ‘-r FILE’ (read from a file)

Limit the Number of Captured Packets

- ‘-c COUNT’ (count \= num to record)

Don’t Resolve IP Addresses and Port Numbers

- ‘-n’ (avoid making DNS lookups, output address in numeric format)  
- ‘-nn’ (port numbers wont be resolved)

Verbose Output

- ‘-v’, ‘-vv’, ‘-vvv’  
- Look at manpage for detail on how each one gets more verbose

Filtering Expressions

- filtering by Host  
  - host HOSTNAME  
  - host ip  
- Filter by Source/Destination  
  - src host IP, dst host IP  
  - src host HOSTNAME, dst host HOSTNAME  
- Filter by port  
  - Sudo tcpdump… port xx … (x \= port \#)  
- Filtering by Protocol  
  - Sudo tcpdump… xx … (x \= protocol, i.e. icmp, tcp, udp.)  
- Logical Operators  
  - and  
  - or  
  - not

Advanced Filtering

- ‘Pcap-filter’ for more listings  
- Length  
  - greater LENGTH  
  - less LENGTH  
- Binary Operations  
  - & (And)  
  - | (Or)  
  - \! (Not)  
- Header Bytes  
  -  Refer to the contents of any byte in the header using the following syntax  
    - proto\[expr:size\]  
      - proto \= protocol  
      - expr \= byte offset  
      - size \= number of bytes that interest us  
- TCP flags field  
  - tcp\[tcpflags\] refer to the TCP flags field  
    - tcp-syn TCP SYN (Synchronize)  
    - tcp-ack TCP ACK (Acknowledge)  
    - tcp-fin TCP FIN (Finish)  
    - tcp-rst TCP RST (Reset)  
    - tcp-push TCP Push

Displaying Packets

- Many formats including:  
  \-q: Quick output; print brief packet information  
  \-e: Print the link-level header  
  \-A: Show packet data in ASCII  
  \-xx: Show packet data in hexadecimal format, referred to as hex  
  \-X: Show packet headers and data in hex and ASCII

Example Reference: traffic.pcap is a file output that was saved. Instead of doing a capture, using presaved output

Examples

- Capture all the packets exchanged with example.com and save them to http.pcap  
  - ‘sudo tcpdump host example.com \-w http.pcap’  
- DNS queries read by a network card  
  - ‘sudo tcpdump \-i ens5 port 53 \-n’  
- Filter by icmp  
  - ‘sudo tcpdump \-i ens5 icmp \-n’  
- Captures all packets except TCP  
  - ‘… tcpdump not tcp’  
- How many packets in traffic.pcap use the ICMP protocol  
  - ‘ tcpdump \-r traffic.pcap icmp \-n | wc’  
- What is the IP address of the host that asked for the MAC address of 192.168.124.137  
  - tcpdump \-r traffic.pcap arp and host 192.168.124.137  
- What hostname (subdomain) appears in the first DNS query  
  - sudo tcpdump \-r traffic.pcap port 53 \-A \-c 10

Advanced Filtering Examples

- ether\[0\] & 1 \!= 0  
  - takes the first byte in the Ethernet header and the decimal number 1  
  - applies the & binary operation. Return true if the result is not equal to the number 0 (i.e., 0000 0000\)  
- ip\[0\] & 0xf \!= 5  
  -  the first byte in the IP header and compares it with the hexadecimal number F (i.e., 0000 1111 in binary)  
  - Return true if the result is not equal to the (decimal) number 5 (i.e., 0000 0101 in binary)  
  - The purpose of this filter is to catch all IP packets with options.  
- What is the IP address of the host that sent packets larger than 15000 bytes  
  - sudo tcpdump \-r traffic.pcap 'greater 15000' \-n  
- tcpdump "tcp\[tcpflags\] \== tcp-syn"  
  - Capture TCP packets with only the SYN (Synchronize) flag set, while all the other flags are unset  
- sudo tcpdump \-r traffic.pcap 'tcp\[tcpflags\] \= tcp-rst' | wc  
  - How many packets have only the TCP Reset (RST) flag set  
- What is the MAC address of the host that sent an ARP request  
  - sudo tcpdump \-r traffic.pcap \-e arp \-n
