Password Attacks

- Online attacks  
  - Pentester attempts authentication directly against a running service such as SSH, FTP, SMB, VPN, or a web login page.  
  - Slower and may trigger alerts, rate limits, or account lockouts, but they require no prior breach.  
- Offline attacks  
  - Obtaining password hashes or encrypted credential stores.  
  - These can be cracked locally without interacting with the target, making them far faster and stealthier.  
  - Offline cracking is usually preferred whenever hashes are available.  
- Types  
  - Basic brute force  
    - Attempt every possible character combination.  
  - Dictionary attacks  
    - Use curated wordlists containing real passwords, leaked credentials, and common patterns.  
      - ex) Rockyou.txt a most well-known wordlist, containing more than 14 million leaked passwords.  
  - Hybrid attacks  
    - Modify dictionary wordlist entries by adding numbers, symbols, capitalization changes, or patterns such as seasons or company names to each word  
  - Password Spray  
    - Try a common password on many different accounts

Hydra

- Online password-guessing tool used by pentesters to test login services such as SSH, FTP, SMB, RDP, HTTP forms, and more.  
- It performs dictionary attacks or brute force attempts directly against a live authentication service  
- Steps  
  - Identify the service  
    - Use scanning tools to confirm SSH is running (typically port 22\)  
    - Verify connectivity  
      - ssh user@target\_ip  
  - Prepare inputs  
    - Username list (or single known username)  
    - Password wordlist (example: common passwords, breach lists)  
  - Run Hydra attack  
    - Single user with password list  
      - hydra \-l exampleuser \-P passwords.txt ssh://target\_ip  
    - Multiple users and passwords  
      - hydra \-L users.txt \-P passwords.txt ssh://target\_ip  
  - If you need to specify custom port: hydra \-L users.txt \-P passwords.txt ssh://target\_ip \-s 2222

Slowing the Attacker

- Salting  
  - A random string is appended to the password before hashing. The salt is stored in the database next to the hash.  
  - Make rainbow table useless  
- Key Stretching  
  - Using algorithms like Argon2 or bcrypt that run the hash function several iterations. This makes each guess take 100ms instead of 0.000001ms, effectively killing brute-force attempts.

