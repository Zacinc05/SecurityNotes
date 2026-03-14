Hash

- Cryptographic hash function converts data of any size into a fixed-length output  
- Used for  
  - Password storage  
  - File integrity checking  
  - Digital signatures  
  - Blockchain systems  
- If they can be cracked, plaintext credentials are revealed

Obtaining Hashes

- Compromised web application databases  
- Found hard-coded into a script  
- Windows SAM or Active Directory dumps (will be covered in later modules)  
- Linux /etc/shadow file (should not be world-readable)  
- Backup archives or configuration files  
- Memory dumps or credential caches

Offline Cracking

- Identifying the hash type  
- Selecting appropriate wordlists or attack modes  
- Running cracking tools locally  
- Testing cracked credentials against systems

Breaking Hashes

- Pre-image Attack  
  - Trying to find the original input that created a specific hash. This is what we do when we "crack" a password. (What we will mainly be doing)  
- Collision Attack  
  - Finding two different inputs that produce the same hash.  
- Rainbow Tables  
  - pre-computed lists of billions of hashes to "de-hash" the passwords instantly

Encode base64

- base64 file\_name

Decode base64

- base64 \-d file\_name

Hashcat

- High-performance password cracking tool used by penetration testers to recover plaintext passwords from captured hashes  
- Go-to tool used primarily for offline cracking  
- Once identified, you need the Hashcat mode number for that particular hashing algorithm  
- Find Modes  
  - Running hashcat \--help  
  - Checking official Hashcat example hash lists  
  - Searching: “hashcat mode NTLM” online

[https://hashcat.net/wiki/doku.php?id=example\_hashes](https://hashcat.net/wiki/doku.php?id=example_hashes)  
