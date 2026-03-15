https://tryhackme.com/room/idsfundamentals

IDS (Intrusion Detection System)

- Detect the activities of connections that passed through the firewall

IDS Types

- HIDS (Host Intrusion Detection System (HIDS)  
  - Monitor system activity  
    - System state, system calls, file modifications, application logs, etc.  
  - Visibility of host’s activities  
- NIDS (Network Intrusion Detection System)  
  - Malicious activities within the whole network  
  - Regardless of host

Detection Modes

- Signature-Based  
  - Signatures are preserved by the IDS in their databases  
    - If the same attack happens later, it gets detected by signature  
  - Unable to detect zero-day attacks  
    - Signature not recognized, won't be stored  
  - Quick  
- Anomaly-Based  
  - Learns normal behavior of the network/system  
  - Preform detection for deviation in normal behaviour  
  - May generate more false positives  
    - Fine tune to correct  
  - High process overhead  
- Hybrid  
  - Combines signature and Anomaly based
