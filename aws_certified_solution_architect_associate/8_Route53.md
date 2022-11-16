# Route 53 Overview
## What is DNS
Domain Name System is the phonebook of the internet. It maps human readable domain names (i.e google.com) to machine readable IP adresses (i.e http://82.124.53.1)
## IPv4 VS IPv6
IPv4 are running out, its space is 32 bits so 4 billion different address. To solve the depletion, IPv6 was created with a space of 128 bits so 340 undecillion addresses (enough to fill the sun with grains of sand, each grain being an address).
## Top level domain (TLD)
In the domain name, it's the last letters after the dot (i.e .com, .fr, .edu, .io, ...). Sometimes you can have second level-domain names which are optional (ie .co.uk, .gov.uk). 
Top level domain names are controlles by the Internet Assigned Number Authority (IANA), a database of all available top level domains.
## Domain Registrars
Authority making sure every domain name is unique. These domain are then registered with InterNIC, a service of ICANN. Each domain is then registered in a central database known as the WHOIS database. AWS is a domain registrar now along with other popular registrar like domain.com, GoDaddy, Hoover, Namecheap...
## Common DNS record types
### SOA (Start of Authority) records
This is where your DNA starts.
SOA stores information about:
- The name of the server that supplies the data for the zone
- The administrator of the zone
- The current version of the data file
- The default number of seconds for the time-to-live file on resource records

### NS (Name Server) records
This is where the DNS information is stored 
What happens when someone looks a website up ?
client types google.com -> The browser goes to the TLD .com record and looks up google.com and it'll give us the NS record for the query (i.e ns.awsdns.com) -> The browser will go over the NS record and get the SOA

### A record or Address Record
Translate domain names into IPv4 or IPv6 address

## TTL (Time To Live)
The time the DNS record is cached on the user local PC. The lower the TTL the faster it is to propagate a DNS record change (for example when we change the IPv4 address to IPv6 or for server migration). If you plan a server migration it is good practice to lower the TTL from 48 hours to 5 minutes and wait a couple of days before migration. That way when updating the A record the change will propagate in 5 minutes instead of 48 hours.

## CNAME (Canonical Name)
Used to map one domain name to another. For example you might want those addresses to resolve to the same site:
- http://m.acloud.guru
- http://mobile.acloud.guru

## Alias Records
Used to map resources within AWS