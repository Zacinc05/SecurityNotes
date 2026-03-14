PGP

- Pretty Good Privacy  
- Software that implements encryption for encrypting files, performing digital signing, and more

GPG

- [https://gnupg.org/](https://gnupg.org/) (known as GnuPG or GPG)  
- Open-source implementation of the OpenPGP standard  
- Commonly used in email to protect the confidentiality of the email messages.   
- Can be used to sign an email message and confirm its integrity

Uses

- GPG to decrypt files in CTFs  
- With PGP/GPG, private keys can be protected with passphrases in a similar way that we protect SSH private keys. If the key is passphrase protected, you can attempt to crack it using John the Ripper and gpg2john.

Decrypt

- Scenario. You have encrypted message ‘message.gpg’ and key ‘backup.key’  
- Import the key to gpg  
  - gpg \--import backup.key  
- Now able to decrypt the message  
  - gpg \--decrypt message.gpg
