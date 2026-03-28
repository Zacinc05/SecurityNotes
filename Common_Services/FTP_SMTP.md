File Transfer Protocol (FTP) 

FTP (File Transfer Protocol)

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

FTP Basic commands

- USER is used to input the username  
- PASS is used to enter the password  
- RETR (retrieve) is used to download a file from the FTP server to the client.  
- STOR (store) is used to upload a file from the client to the FTP server.

SMTP (Simple Mail Transfer Protocol)

- Defines how a mail client talks with a mail server and how a mail server talks with another

SMTP basic commands

- HELO or EHLO initiates an SMTP session  
- MAIL FROM specifies the sender’s email address  
- RCPT TO specifies the recipient’s email address  
- DATA indicates that the client will begin sending the content of the email message  
- . is sent on a line by itself to indicate the end of the email message

