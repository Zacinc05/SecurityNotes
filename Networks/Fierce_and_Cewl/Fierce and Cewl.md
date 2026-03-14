Fierce

- Find host names  
- Available from kali as ‘fierce –help’  
- /usr/bin/fierce (this slide is important for lab 4\. Take a look in these files for the lab. The actual executable scripts are important)  
- Run fierce  
  - Fierce –domain cise.ufl.edu  
  - Fierce tries to do a zone transfer from each of these nameservers, but fails  
  - Looks for wildcard record  
  - List as many common hostnames as it cat  
  - Has a default list of common names  
  - If finds, checks similar ip range for lookup  
  - To check everything, fierce \-travarse 255 (all ip in /24 network)

Cewl

- Cewl wordlist  
  - grabs all strings that are x characters or longer. Will yield a huge word list.  
  - Takes longer to run this wordlist with fierce, but more results  
- ex)  
  - cewl https://www.cise.ufl.edu \-d 3 \-o —w cise-wordlist  
  - This looks 3 pages deep and grabs all strings 3 characters or longer.  
  - Running fierce with these words takes longer, but yields more undiscovered hostnames (such as cyclone.cise.ufl.edu

