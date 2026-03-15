https://tryhackme.com/room/firewallfundamentals

Purpose

- Incoming/Outgoing traffic security 

Types

- Stateless  
  - Filtering by predetermined rules  
  - Quick, not complex  
  - OSI layer 3 & 4 (Transport/Network)  
- Stateful  
  - Track previous connection  
    - Store in a state table  
  - Inspect packets based on history w/ connections (patterns)  
  - Allows complex rules  
  - OSI layer 3 & 4 (Transport/Network)  
- Proxy  
  - Between private network and Internet  
  - Inspect data inside packets  
  - Content filtering options  
  - Provide application control  
  - OSI layer 7 (Application-level gateways)  
- NGFW (Next-Generation)  
  - Deep packet inspection  
  - Has IPS  
  - Block malicious activity in real time  
  - Identify anomalies  
  - Decrypt/Inspect SSL/TLS data packet  
  - OSI layer 3-7

Firewall Rules

- Source address  
- Destination address  
- Port  
- Protocol (what to use for communication)  
- Action (allow/deny/forward)  
- Direction (in/outbound)

Firewall Actions

- Allow  
- Deny  
- Forward (redirect traffic to different network segment)

Rule Directionality

- Inbound  
- Outbound  
- Forward  
  - Forward specific traffic inside the network
