NTHash / NTLM

- Hash format modern Windows operating system machines use to store user and service passwords

SAM (Security Account Manager)

- Used to store user account information, including usernames and hashed passwords  
- Acquire NTHash/NTLM hashes by dumping the SAM database on a Windows machine  
  - using a tool like Mimikatz  
  - using the Active Directory database: NTDS.dit
