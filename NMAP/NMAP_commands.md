Ping/ICMP scan   
nmap \-sp 192.168.1.1/24 (ip address/subnet mask)   
Scans for hosts in the specified range. Doesn’t scan ports finds computers such as   
phones/computers/shit 

Single host scan  
nmap \<target\>   
Examines a single host for 1000 well known ports 

Stealth Scan/SYN scan   
Nmap \-sS \<target\>   
nmap \-sS 192.168.1.1 //Single host   
nmap \-sS \-p 80 192.168.1.1 //Scan a host’s port   
nmap \-sS \-p 22,80,443 192.168.1.1//Scan multiple ports   
nmap \-sS \-p 1-1000 192.168.1.1 //Scan a port range   
nmap \-sS 192.168.1.0/24 // Scan an entire subnet   
nmap \-sS \-sV 192.168.1.1 // Enable service/version detection with SYN scan: 

NULL FIN and XMAS used for Firewall Evasion   
Null scan that sends a tcp with no flags, target should respond with RST if closed   
nmap \-sN \<target\>   
FIN scans (-sF) a request is sent with the FIN flag, target RST if the port is closed.   
nmap \-sF \<target\>   
XMAS Scans send a malformed TCP packet and expects a RST response for closed ports. It's   
referred to as an xmas scan as the flags that it sets (PSH, URG and FIN)   
nmap \-sX \<target\> 

Version scan   
nmap \-sV \<target\> 

OS detection   
nmap \-O \<target\>   
nmap \-O \--osscan-limit \<target\>   
(Requires Root, run with sudo)   
Sudo nmap \-O \<target\> 

Aggressive scanning (easier to detect)   
nmap \-A \<target\>   
Includes OS detection, Version Detection, Script Scanning, Traceroute 

Timing of scans    
nmap \-T5 \<target\>   
Sets speed to tier 5 

Scanning multiple devices   
Js list a bunch on 1 line   
nmap \<ip\_address 1\> \<ip\_address 2\> \<ip\_address 3\>   
Use a wild card   
nmap 192.168.1.\*   
Use commas   
nmap 192.168.1.0,1,2,3,4   
Use a range   
nmap 192.168.1.0-255   
Scans all ports   
nmap \-p- \<target\> 

Port Scanning   
nmap \-p \<port\_number\> \<target\>    
(target can be any host/ip address, important part is the \-p \<port\_number\>)   
Scanning for TCP connection   
nmap \-p T:\<port\_number\>   
Scan a range   
nmap \-p 0-255   
Scan top \_\_\_ most common ports   
nmap \--top-ports \<num\_ports\> 

Scanning from a file   
nmap \-iL ./input.txt (scans ip addresses from a file)   
Verbosity   
nmap \-v \<target\>   
Gives more readable output   
nmap \-vv \<target\>   
Verbosity 2   
Save scanning results to a file   
nmap \-oN output.txt \<target\>    
Saves scan results to output.txt   
nmap \-oX output.xml \<target\>   
Saves scan results in XML format   
Nmap \-oA output \<target\>   
Saves scan results in default nmap format, XML, and grepable format   
output.nmap, output.xml, output.gnmap 

See which IP addresses contain active hosts/Ping Sweep   
nmap \-sn 192.168.0.1-254   
or   
nmap \-sn 192.168.0.0/24 \-sn tells nmap not to scan ports and send only ICMP echo packets/ping requests   
   
SCRIPT SCAN://Legit js copied n pasted from command line   
Activates a script    
nmap  \--script=\<name\> \<target\>   
Activates multiple scripts   
nmap –script=\<name,name,name\> target   
             \--script-args= \<n1=v1,\[n2=v2,...\]\>: provide arguments to scripts   
             \--script-args-file=filename: provide NSE script args in a file   
             \--script-trace: Show all data sent and received   
Shows he;p   
nmap \--script-help \<script-name\>   
safe:- Won't affect the target   
intrusive:- Not safe: likely to affect the target   
vuln:- Scan for vulnerabilities   
exploit:- Attempt to exploit a vulnerability   
auth:- Attempt to bypass authentication for running services (e.g. Log into an FTP server   
anonymously)   
brute:- Attempt to bruteforce credentials for running services   
discovery:- Attempt to query running services for further information about the network (e.g.   
query an SNMP server).   
