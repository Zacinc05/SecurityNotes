POP3 (Post Office Protocol version 3\)

- Designed to allow the client to communicate with a mail server and retrieve email messages  
- Email client sends its messages by relying on SMTP and retrieves them using POP3  
- Listens on TCP port 110 by default

POP3 Basic commands

- USER \<username\> identifies the user  
- PASS \<password\> provides the user’s password  
- STAT requests the number of messages and total size  
- LIST lists all messages and their sizes  
- RETR \<message\_number\> retrieves the specified message  
- DELE \<message\_number\> marks a message for deletion  
- QUIT ends the POP3 session applying changes, such as deletions

POP usage

- example)

  root@ip-10-65-110-1:\~\# telnet 10.65.178.141 110

  Trying 10.65.178.141...

  Connected to 10.65.178.141.

  Escape character is '^\]'.

  \+OK \[XCLIENT\] Dovecot (Ubuntu) ready.

  AUTH

  \+OK

  PLAIN

  .

  USER linda

  \+OK

  PASS Pa$$123

  \+OK Logged in.

- Connect to telnet with port 110  
- ‘AUTH’ to sign in  
- USER \<user\> to send username  
- PASS \<pass\> for password

IMAP (Internet Message Access Protocol)

- Synchronizing read, moved, and deleted messages  
- Use more storage than POP3 as email is kept on the server and synchronized across the email clients

IMAP Basic commands

- LOGIN \<username\> \<password\> authenticates the user  
- SELECT \<mailbox\> selects the mailbox folder to work with  
- FETCH \<mail\_number\> \<data\_item\_name\> Example fetch 3 body\[\] to fetch message number 3, header and body.  
- MOVE \<sequence\_set\> \<mailbox\> moves the specified messages to another mailbox  
- COPY \<sequence\_set\> \<data\_item\_name\> copies the specified messages to another mailbox  
- LOGOUT logs out

