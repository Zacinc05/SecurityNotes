Linux offers the functionality of a built in firewall

Netfilter

- Framework inside the Linux OS  
- Foundation for firewall utilities in Linux to control network traffic  
  - iptables  
    - functionalities to control network traffic  
  - nftables  
    - Successor to the “iptables” utility  
    - Enhanced packet filtering and NAT capabilities  
  - firewalld  
    - Predefined rule sets  
    - Pre-built network zone configurations

Ufw

- Remove complications of making rules in complex syntax  
- Easier interface than iptables  
- ex)  
  - Status of ufw firewall  
    - sudo ufw status  
  - Enable ufw firewall  
    - sudo ufw enable  
  - Allow outgoing traffic  
    - sudo ufw default allow outgoing

