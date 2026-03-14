Traceroute

- Tries to find all hosts on the network between local host and some destination host  
- Done by sending packets with TTLs increasing from 1 up to 30\.  
- For each different TTL, 3 packets are sent.  
- As each packet expires, it should receive an ICMP Time Exceeded reply from the host at which it arrived.  
- Traceroute waits 5 seconds for each expiration.  
- If 5 seconds is exceeded, a \* is printed.  
- Otherwise, if a host responds with the Time-to-Live Exceeded message, then traceroute prints the TTL value, host IP address, and round-trip time of each probe.

Wireshark

- Packet sniffing and analysis tool  
- Sniff packets by selecting an interface on which to sniff. You must be root, or a member of a privileged group to do raw packet captures.  
- It will show you the packets that it captures on that interface.

Using Wireshark

- Bottom left notepad to read details

	![][image1]

Packet Dissection / protocol dissection

- Investigates packet details by decoding available protocols and fields

Packet Numbers

- Calculates the number of investigated packets and assigns a unique number for each packet

Find Packets

- Edit \--\> Find Packet

Mark Packets

- “Edit" or the "right-click" menu to mark/unmark packets

Export Packets

- Under “File”

Export Objects

- Under “File”  
- Packets or entire Objects (files)  
- Can filter for certain file types  
- Ex) find a .txt file within the wireshark capture:  
  File \-\> Export Objects \-\> HTML \> text filter: “.txt”

Time Display Format

- “View” \--\> Time Display Format"

Expert Info

- “Analyze” → Expert Information  
- Wireshark detects specific states of protocols to help analysts easily spot possible anomalies and problems (still consider false positive/negative)  
- Chat	Blue	Information on usual workflow.  
- Note	Cyan	Notable events like application error codes.  
- Warn	Yellow	Warnings like unusual error codes or problem statements.  
- Error	Red	Problems like malformed packets.

Packet Filtering

- Wireshark has two types of filtering approaches  
  - capture filter  
  - display filters  
- Filters are specific queries designed for protocols available in Wireshark's official protocol reference  
  - Apply as Filter  
    - Use “right-click menu” or "Analyse \--\> Apply as Filter" menu to filter the specific value  
  - Conversation Filter  
    - "Conversation Filter" option helps you view only the related packets and hide the rest of the packets easily  
    - "right-click menu" or "Analyse \--\> Conversation Filter" menu  
  - Prepare as Filter  
    - create display filters using the "right-click" menu  
    - adds the required query to the pane and waits for the execution command (enter) or another chosen filtering option by using the ".. and/or.." from the "right-click menu"

Packet Layers

- The Frame (Layer 1\)  
  - This will show you what frame/packet you are looking at and details specific to the Physical layer of the OSI model.  
- Source \[MAC\] (Layer 2\)  
  - This will show you the source and destination MAC Addresses; from the Data Link layer of the OSI model.  
- Source \[IP\] (Layer 3\)  
  - This will show you the source and destination IPv4 Addresses; from the Network layer of the OSI model.  
- Protocol (Layer 4\)  
  - This will show you details of the protocol used (UDP/TCP) and source and destination ports; from the Transport layer of the OSI model.  
- Protocol Errors  
  - This continuation of the 4th layer shows specific segments from TCP that needed to be reassembled.  
- Application Protocol (Layer 5\)  
  - This will show details specific to the protocol used, such as HTTP, FTP,  and SMB. From the Application layer of the OSI model.  
- Application Data  
  - This extension of the 5th layer can show the application-specific data.

Documentation

- https://www.wireshark.org/docs/

[image1]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAIkAAAA7CAYAAABPJqm3AAAGqElEQVR4Xu3b6VcTZxTHcf3fFBdUqqhIi6CoVUBk0wpVtFZr64K49LS1WutyrEDBbkelVY+IC0QQhYgEsgHBYxEJQfb2Rcv8hnuZTEZHkgzael98XmRm4jMm33OeZ2bCjLGxv/9RVFZWstHRURgZGTFVVlYGSUlJIfTHGqGxqqur2VTGF9abIZEIM4aR0M7h4eHXVlpayigS/TFGaKybN2+ycMYX1pFIhCmJRJgyjIR2Dg0NhaWkpAT0243QWNpIIh1fRJdEIkwZRkI7BwcHLUdjaSOZzvGFOYlEmDKMhHYODAxYjsaqqqpi0zm+MCeRCFOvjGQ6GUUi3g4SiTAlkQhThpEIoSWRCFMcSV9fnxCGJBJhSiIRpiQSYUoiEaYkEmFKIhGmLIqkf4J+u3X8fj/T77PSq8dUPwejYwKBAIS+5+0jkUTo1WNKJKb8AZV+u4I+pC5fB5z64gDbnrwKNs6eAxmzYoC2K77bdwDo/UaRBPz9oB87Gu7a2yCrvA7SSu/BmguTVp6zQcJpVfypWrbwZA0UX1Lpz11x5coVyMvLgYryEqY/HytJJGGSSKImeNqhMBQ3L12C3JiFcC55NbudswUchbvg8cfboSotk51ZsQJy5y4C+vcUNG7Ar4SiP6foqG5shY2/qdb9qsr9w80cz/oh47IH5p9tYbPONEPc8RvQ0tIMFRU/MputBgoKtkJOXjbTn4+VJJIwSSRRI5FIJFOk/SI/WbAIbFu2Quf+g5OKDqkmXrfv2Qvewp3Mk78Nbq3NgMLYBWwyltBziIR23XOrqRXyrzkh64oLuvsH2dhfQ5BQ0QZxF1pY7HknLDxeBbuOHINlCUtYyuokuHPnDtAaRaE/NytJJFMgkRjsjBZfZztkx8xnd7PyoGPPPlVRMfMd+xI6io6A97N94Nnx6aSJSFw5m6Fq1VqWMycWujp9oD+faLC3ueG6pzfI6NhgiEq3Hy40P2dn7T1QeOIHWLZisUoTCaHpRzu+0dWQVSSSMEkkEesNQvc0TieuZN6du4Gmko6DRazz0GGg13SMNhJvwXZw5m4GR/omdjIuHmjc0POLnNfrBn0QWiOjL0C/XfHzL+WgD0Lr6NHDoL8AUEgkEsm7FIn6mu6S3vgwnbm3FYLnk91AU4qife9+8H6+D+gYz/Ydkz7Kh7asXGhN28R+X5EENG7o+YUnEPAzimR4eBCa7A3g8bjYE18XNDU9hFPff8uWj0eg0IdRVlbCbDYb0Ph0B/tld7GtIpFMgURisDN8EolE8trUuXRjzGywZ2YzujrhWLRXLjp8TH4Bc+ZtUaVng2NdGmtIWg30gDD0vCLnaXfDwFAAmpvt4HK1MY9XNbn+WKoRHMfZc6dgdGyAcSS9ftBG8j9YkxCJRCJ5Cf1/IDNmLjSmZTDX+BescG/ZChQNwhm/alG4lPsgyuuJY+hKBjJzoHV9JjhS17H77yeDpZF4PDAw2BdkaLif1d+vheLiIvjq66OM4igtOw8jowMh9NON9tmX/nysJJGESSKJGnUBSwvIq0kpzJmRrcrOA7pzChMBuZTt42hxyu8ZR3G0rtmgSkpllxcvg2gvXLVocRro74F7dXfB3tzENm/OhZkzZ0JWVia7eLEcHj1qCqKNbDIS9XOUSCSSdzUSFd35PPFePGsdvwxWtG3YpErPYhQCb5s4ht6jcKSuVyWnwuPEFHZ83gKw8o4rRdLX9xQcrXagxaoiNnYepKdvgIs/lbI252Pg49ud8GLIzyYjCb3jOp0kkjBJJFEmkUgkpugX7fQIX3Fj+QfgSE0DXlsYoCBaUtYxjiMhGa7FLWX8U4GJcfXnEw0USW+vDzo726C7u4P1PvNBV5cLOjpamM/nBDr2z24f0BpHob+6CTZ94UgkYZJIoozum2h/vrgjZj5cX5oI9KUbSlwFFISiZTwwxdVFS6Bw9jxm1c8XtSiSnh4vPGiwgf1RA6MQGpvq4WFjHWt4YIPKysvQ1FgPNH0pKJI3cUWjJZGESSKJ0Ov8KQN9kTQ10GJTcTkuHuqWJAa5NB4D+WZuLND7tQHqx7ICRfK8ux1ouqGpRdHZ6QCvtwXcbjujgJ4+dcOTJyqavhSh003wj7m0T9qtJJGESSKJmPmiip5m0o+V6XJVsW1lCtDfANMzGNquoGPpR9ZTHT9STmcr1NZWwT3bbaiprWa0r6bmxoTrjPfRsbZbIerr60E/9nSTSMIkkUTM/EuSSN75SF5manOpfm1Dr4O2veGV/1RM/QHd639WVpJIptF/NZJ/Aa9OVkkpzdMZAAAAAElFTkSuQmCC>
