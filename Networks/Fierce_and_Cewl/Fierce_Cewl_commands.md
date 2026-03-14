cewl \<target\> \-d 3 \-o \-w output   
This looks 3 pages deep and grabs all strings 3 characters or longer, and outputs it to a file   
called output   
   
fierce \--domain \<target\>   
Finds subdomains   
“Show me what DNS information and subdomains I can discover about this domain.”   
   
fierce \--domain \<target\> \--subdomain-file \<input\_wordlist\>   
Fierce uses an input wordlist to find subdomains on a target   
fierce \--domain example.com \--dns-axfr \--dns-axfr does a zone transfer   
dig ns artstailor.com   
traceroute \-I \<target\> 
