John the Ripper

- Tool for conducting fast brute force attacks on various hash types  
- Dictionary attack

Jumbo John

- Popular community enhanced version  
- Test password strength and detect weak Unix passwords

John Basic Syntax

- ‘john \[options\] \[file path\]’  
- Automatic Cracking  
  - john \--wordlist=\[path to wordlist\] \[path to file\]  
- Format-Specific Cracking  
  - john \--format=\[format\] \--wordlist=\[path to wordlist\] \[path to file\]  
  - Use something like hashid to get the format

Cracking Hashes from /etc/shadow

- Unshadowing  
- John is particular about the formats. To crack /etc/shadow passwords, combine it with the /etc/passwd file for John to understand the data it’s being given  
- ‘unshadow \[path to passwd\] \[path to shadow\]’  
- Usually feed to an output file and then john the output file to crack passwords

Single Crack Mode

- John uses only the information provided in the username to try and work out possible passwords heuristically by slightly changing the letters and numbers contained within the username  
- ‘john \--single \--format=\[format\] \[path to file\]’  
- Using  
  - Change format for reading, must know the word to alter  
    From 1efee03cdcb96d90ad48ccc7b8666033  
    To mike:1efee03cdcb96d90ad48ccc7b8666033

Custom Rules

- ‘john \--wordlist=\[path to wordlist\] \--rule=PoloPassword \[path to file\]’  
- Lowercase letter, Uppercase letter, Number, Symbol, etc.  
- Create Custom Rules  
  - \[List.Rules:\_\_\_\_\_\] is used to define the name of your rule  
  - Use a regex style pattern match to define where the word will be modified  
    - Az: Takes the word and appends it with the characters you define  
    - A0: Takes the word and prepends it with the characters you define  
    - c: Capitalises the character positionally  
  - Define what’s appended  
    - \[0-9\]: Will include numbers 0-9  
    - \[0\]: Will include only the number 0  
    - \[A-z\]: Will include both upper and lowercase  
    - \[A-Z\]: Will include only uppercase letters  
    - \[a-z\]: Will include only lowercase letters  
    - ex)  
      - \[\!£$%@\]: Will include the symbols \!, £, $, %, and @  
      - Add all capital letters to the end of the word  
        - Az"\[A-Z\]"

Zip2John

- Convert aZip file into a hash format that John can understand and hopefully crack  
- ‘zip2john \[options\] \[zip file\] \> \[output file\]’  
- Will then have to john the output file to get the password  
- Similar to unshadow

Rar2John

- Like Zip2John but for Rar files

SSH2John

- SSH Key Passwords  
- Using John to crack the SSH private key password of id\_rsa files  
- ‘ssh2john \[id\_rsa private key file\] \> \[output file\]’  
- If you don’t have ssh2john installed:  
  - ‘/opt/john/ssh2john.py’  
  - ‘python /usr/share/john/ssh2john.py’  
  - ‘python3 /opt/john/ssh2john.py’  
- Like rar2 and zip2, john the output file

John example

- SHA-256  
  - john \--format=raw-sha256 \--wordlist=/usr/share/wordlists/rockyou.txt hash3.txt  
- NTHash / NTLM  
  - john \--format=nt \--wordlist=/usr/share/wordlists/rockyou.txt ntlm.txt  
- Unshadow  
  - unshadow local\_passwd local\_shadow \> unshadowed.txt  
  - john \--wordlist=rockyou.txt \--format=sha512crypt unshadowed.txt  
- Single crack  
  - john \--single \--format=raw-md5 hash07.txt  
- Custom rules from PoloPassword file  
  - john \--wordlist=\[path to wordlist\] \--rule=PoloPassword \[path to file\]  
- Zip2john  
  - zip2john zipfile.zip \> zip\_hash.txt  
  - john \--wordlist=/usr/share/wordlists/rockyou.txt zip\_hash.txt
