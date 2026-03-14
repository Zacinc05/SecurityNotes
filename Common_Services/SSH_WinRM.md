SSH (Secure Shell)

- Get a shell on a remote machine  
- TCP 22: standard ssh access port  
- Used for secure remote command line access, remote command exe, and encrypted file transfers  
- ‘Admin key” for almost every linux server  
- Tools  
  - ssh \<username\>@\<target\_ip\>  
  - ssh \<username\>@\<target\_ip\> ‘command’		(run single command)  
  - scp localfile \<username\>@\<target\_ip\>:/home/user	(copy file to server)  
  - scp \<username\>@\<target\_ip\>:/home/user/fille	(copy file from server)

WinRM

- Get a shell on a windows target  
- Powers PowerShell Remoting, allow users ot exe scripts, manage config, and gather system data across entire enterprise network  
- TCP 5985: HTTP  
- TCP 5986: HTTPS  
- Tools  
  - Establish Connection: evil-winrm \-i \<target\_IP\> \-u \<username\> \-p \<password\> (Starts a remote PowerShell session).  
  - Execute Remote Script: evil-winrm \-i \<target\_IP\> \-u \<username\> \-p \<password\> \-s /path/to/scripts/ (Loads local scripts into the remote session).  
  - Download a File: download \<remote\_path\> \<local\_path\> (Retrieves files from the Windows host).  
  - Upload a File: upload \<local\_path\> \<remote\_path\> (Transfers tools or files to the target).  
  - Exit Session: exit.
