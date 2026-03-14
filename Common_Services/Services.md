HTTP: Websites  
SSH/RDP: Remote Access  
MySQL/MSSQL: Databases

CVE (Common Vulnerability & Exposure)

- Research process professionals take to find/give flaws  
  - Discovery  
    - Find flaw  
  - Reporting (responsible disclosure)  
    - Go to software company and show finding  
    - Wait (for vendor to patch/remediate) before public  
  - Assignment  
    - CNA (CVE Numbering Authority)  
      - ex) MITRE  
    - CNA will assign id and date to reported flaw  
    - Ensures everyone has a universal way to reference previously found bugs  
  - Publication  
    - Once a fix is ready or vendor fails to respond  
    - CVE published in NVD (National Vulnerability Database)  
    - Given a CVSS score 0-10  
      - Based on ease/impact of exploitability  
    - Researchers can post POC code and write ups, allowing others to see how to exploit previous (unpatched) versions

Outdated software

- Steps to find  
- Fingerprinting  
  - Use tools like nmap \-sV or banner grabbing via nc to find version of a service  
- Search for CVE  
  - Search for that specific version in vulnerability databases  
- POC (proof of concept)  
  - Look for "PoC code", which is a script or set of commands that successfully demonstrates the exploit  
- If you see an outdated version, your first instinct should be:  
  Search Engine → "Service Name \[Version\] CVE" → "CVE-XXX-YYYY PoC GitHub"

Common Services

- DNS (Domain Name Services)  
  - Translate domain names into IP addresses  
    - UDP 53  
      - Standard Queries  
      - Fast  
    - TCP 53  
      - Zone transfers  
      - Slower  
  - Query based  
    - Use of dig for footprinting (idea of where we are)  
      - IP’s, mail servers, reverse lookup (IP to domain name), trace (where DNS resolves)  
  - Zone Transfers  
    - AXFR (DNS Zone Transfer)  
      - Transferring DBS records between primary and secondary server  
  - Lame Delegation  
    - Domain hijacking  
    - Domains Name Server (NS) records point to a provider or IP addr that is no longer active  
      - Discover  
        - Dig ns \<domain\_name\>  
      - Identify Lame Entry  
        - SERVFAIL  
        - NXDOMAIN  
      - Take it over  
        - purchase/claim  
      - Verify with dig \<domain\_name\>  
  - Cache Poisoning  
    - Insert malicious, invalid data into a cache  
  - FTP (File Transfer Protocol)  
    - TCP 21 (Control)  
      - Sending commands and receive status codes  
    - TCP 20 (Data)  
      - Actual transfer of file data in ‘active’ mode  
    - Bulk file transfer, website maintenance, distribute software packages  
    - Stateful and Clear-Text Protocol  
      - Visible to anyone sniffing the network traffic  
    - Tools:  
      - Establish connection  
        - dtp \<target\_ip\>  
      - List files  
        - ls \-R  
      - Download FIle  
        - Get filename.txt  
      - Upload File  
        - put local\_file.txt  
      - Exit session  
        - bye/exit  
- FTP: Anonymous Login  
  - Legacy configuration  
    - Server allows access without a unique user account  
    - Easy to share, not secure. Shouldn’t be left on  
      - Often misconfigured  
- Tools  
  - Check for vulnerability  
    - nmap \-sV –script ftp-anon \<target\>  
  - Manual login  
    - ftp \<target\> (username: anonymous, Password: \[any\])  
  - Recursive Enumeration  
    - ls \-R (map folder structure)  
  - Overwrite data  
    - put file\_a sensitive.txt  
- Create dir  
  - mkdir staging\_area  
- FTP: Path Traversal  
  - Steps  
    - Navigate to root  
    - Access system files  
    - Locate SSH keys

