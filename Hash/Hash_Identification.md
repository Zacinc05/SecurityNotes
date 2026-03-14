[https://hashcat.net/wiki/doku.php?id=example\_hashes](https://hashcat.net/wiki/doku.php?id=example_hashes)

Identify Hash Types

- Length/Format  
  - 32 hex chars → often MD5  
  - 40 hex chars → often SHA1  
  - 32 hex uppercase → often NTLM  
- Context  
  - Windows dump → often NTLM  
  - Linux /etc/shadow → often SHA512crypt or bcrypt  
- Identification tools  
  - hashid  
    - py \-m hashid “message”  
  - hash-identifier  
  - Compare with example hashes from documentation

$y$	yescrypt

$gy$	gost-yescrypt

$7$	scrypt

$2b$, $2y$, $2a$, $2x$     bcrypt

$6$	sha512crypt

$md5	SunMD5

$1$	md5crypt  
