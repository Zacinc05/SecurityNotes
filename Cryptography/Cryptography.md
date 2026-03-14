Cryptology usage

- Authentication → passwords, hashes, SSH keys  
- Confidentiality → HTTPS, VPNs, encrypted disks  
- Integrity → digital signatures, certificates  
- Storage → password databases

Encoding vs. Encryption

- Encoding  
  - Public transformation of data  
  - Usability, not secrecy  
- Encryption  
  - Transforms data using a secret  
  - Data should be mathematically indistinguishable from random noise  
- Difference example  
  - URL Encoding  
    - Input: Hello World\!  
    - Encoded: Hello%20World%21  
  - Encryption  
    - Input: Hello World\!  
    - Encrypted: ASFAScso0SFHJK4

Base64

- Maps characters and symbols to binary data  
- A-Z, a-z, 0-9, \+, and /  
- Identifying Marks  
  - String of alphanumeric characters containing both upper and lowercase  
  - Commonly ends with \== or \=  
- Reversible and provides zero security

Symmetric Key

- Uses a single shared secret key for both encryption and decryption. Anyone with the key can read the data  
- Look for  
  - Hardcoded encryption keys in source code  
  - Keys stored in configuration files  
  - Weak encryption modes  
  - Reused keys across systems

Asymmetric Key

- Uses two related keys instead of a single shared key  
- Typically used for authentication or secure key exchange rather than bulk data encryption

Operational Considerations

- Start with password spraying instead of full brute force  
- Watch for account lockout policies  
- Reduce threads if the service is unstable  
- Log brute force attempts for reporting and reproducibility  
- Always obtain authorization before performing online attacks
