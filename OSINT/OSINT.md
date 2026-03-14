**OSINT**

Open source intelligence

- The collection and analysis of data gathered from open sources (overt sources and publicly available information) to produce actionable intelligence  
  - Patterns, connections, behaviors without direct access

What counts at “open sources”

- Social media, public records, news articles, blogs, websites, images, video, satellite imagery, academic paper, government report, google, etc.  
- Practical examples: FInding a company’s VPN portal via certificate logs, software version from banners, username lists form linkedin profiles, internal hostnames from internal repos, address by searching background of a social media post

Google Dorking (“Google Hacking”)

- Use of advanced search operators to find sensitive information  
- www.google.com/advanced\_search  
- Using google’s form interface yields a search string that could be sed to do the same thing  
- Ex: Taylor Lautner. Taylor Lautner wife. Taylor Dome.  
  To get red of the husband in search (both have same legal name taylor lautner)  
- Ex: site:ufl.edu filetype:pdf “confidential”.  
  (will eventually find something. Find new classes, programs, etc.)  
  Florida has broad confidential law  
- Github has all kinds of credentials around  
- Common op  
  - Intitle:”index of” \- dictionary listings  
  - site:target.com – Limits results to the target domain.  
  - filetype:pdf (or docx, xlsx, conf) – Finds specific file types.  
  - inurl:admin – Looks for "admin" in the URL.  
  - intitle:"index of" – Finds directory listings (Directory Traversal).  
- Ex  
  - site:target.com filetype:pdf "confidential"  
  - site:target.com inurl:admin  
  - site:github.com "target.com" password

What to look for

- Email is usually revel account name  
- Links can revel unpublished web directories  
- Forums with entities of user can reval hard/soft ware used. Often reveal poorly configured server  
- Job sites can show what a company is looking for. Find what weak in.  
- Open directories on company site reveal useful intel  
- Public repos/documentation reveal API keys.

What to Use

- hunter.io is for email addresses  
- Haveibeenpwned find valid emails  
- Showdan. Scans IPV4 spaces, cameras, open sources, etc. super useful for databases and webcams.  
- Recon-ng. Automate collection of open-source intel by running modules that query public API’s and databases.

Metadata

- Data about data (context)  
- Geolocation (in which GPS coordinates embedded in a photo (i.e. smartphone)  
- Device Fingerprinting (camera serial numbers, software version, or unique settings can link a specific file to a specific person/device)  
- Timeline Analysis (creation/modification timestamps help you verify if a file was altered or establish a sequence of events)

ExifTool

- Industry standard command line utility for reading/writing metadata.  
- Extract hidden details from virtually any file type of to “clean” files by removing sensitive tags  
- Commands:  
  - exiftool image.jpg  
  - exiftool \-gps:all image.jpg  
  - exiftool \-all \= image.jpg  
- Most platform auto strip data for security/storage reasons. Aggressively remove data

DNS (“The Phonebook”)

- Translate domain names into IP addresses  
- Types  
  - A: IPV4  
  - AAAA: IPV6  
  - MX: Mail exchange  
  - NS: Name Serber  
  - TXT: Text records  
  - PTR: Pointer  
  - CNAME: Canonical name (alias)

Recursive vs authoritative DNS Server

- Recursive  
  - Only knows what has ‘cached’  
  - Will ask Authoritative server for the info  
- Authoritative  
  - Ideal place to be  
  - Holds the actual zone file  
  - Know exactly what’s there, they’re the source

Path of DNS request:

- 1\. The ask  
- 2\. The root  
- 3\. The TLD  
- 4\. The authority  
- 5\. The answer

DNS Zones

- Distinct part of domain namespace which is delegated to a legal entity: admin, org, or individual  
- Zone File: like a spreadsheet containing every single record for that domain

DIG and NSlookup

- Identify relationship between host names and IP addresses  
- DIG more common now, NSlookup still used.

Zone Transfers

- DNS Zone Transfers are mechanisms used to synchronize DNS records betw/ a primary DNS Server and 1+ secondary server  
- Synchronize records from 1 main server to multiple secondaries  
- If one server down, another can take over  
- High availability, redundancy  
- Protocol: AXFR (Asynchronous Full Transfer Zone)

Zone Transfer vulnerability

- Often incorrectly configured. Attack by acting as a secondary server.  
- Recon Goldmine, basically getting a network  
- Find hidden, connected, test branches of the network  
- Transfer failed \= configured, cannot steal.  
- This is a crime (unauthorized access).

AXFR (Asynchronous Full Transfer Zone)

- Get everything from primary server to secondary server

Internet Archives

- May not necessarily up to date  
- Gathering information  
- Legacy vulnerability analysis. Business documents.  
- Wayback Machine. Use regex w/ specific search strings. Get a large list of endpoints. Note: on bigger sites this may not work, too many results to look at

NMAP

- Open source tool used for network discovery and security auditing  
- Send specific crafted packages to target, analyzes the response (or lack of) to determine network map

Host Discovery w/ nmap

- What IP address you need. Usually a ping scan / ping sweep  
- Take a range of IP. Ping them all, find what’s active  
- Ping \= send packet, check for send back.  
- Ports \= virtual endpoints where network connections start/end.  
- Knowing open ports tells us what software/services are open.  
- Can scan an IP, range, quick/aggressive, port, etc…

