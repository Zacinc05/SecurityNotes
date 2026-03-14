RDP (Remote Desktop Protocol)

- TCP 3389: RDP traffic  
- Full desktop access, including use of local peripherals  
- Remote control  
- Uses NLA (Network Level Authentication) to secure the connection  
- Tools  
  - Establish Connection: xfreerdp /v:\<target\_IP\> /u:\<username\> /p:\<password\> (Opens the remote desktop window).  
  - Map Local Drive: xfreerdp /v:\<target\_IP\> /u:\<user\> /p:\<pass\> /drive:share,/tmp (Maps your local /tmp folder as a drive on the target).  
  - Enable Clipboard: /clipboard (Appended to the command to allow copy-pasting between host and guest).  
  - Set Resolution: /w:1024 /h:768 (Adjusts the window dimensions for better visibility).  
  - Exit Session: Log off from the Windows Start menu or close the client window.

HTTP/HTTPS (Hypertext Transfer Protocol)

- TCP 80: HTTP  
- TCP 443: HTTPS  
- Used for API’s. Apps, etc.
