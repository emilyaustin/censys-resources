# Censys Search Resources

Head to [Censys Search](https://search.censys.io) to try out some of the searches below. 

We provide 10 free queries a day to unregistered users. Register for a free account and get 250 queries per month, along with API access.


## Search Snippets 🔎
Services in a specific location: \
`services.service_name: MODBUS and location.country:Germany`

Use the `same_service` operator to find services running on a specific port: \
`same_service(services.service_name:HTTP and services.port:1337)`

Exclude pseudoservices (e.g., honeypots) from results by appending `services.truncated:false` to your search query: \
`services.service_name:HTTP and services.truncated:false`

Non-standard services running on common ports:\
`same_service(services.port:{80,22,21} and not services.service_name:{HTTP,SSH,FTP,UNKNOWN}) and services.truncated:false`

Hacked MikroTik routers: \
`services.service_name:MIKROTIK_BW and "hacked"`

Internet-exposed printers: \
`"@PJL INFO STATUS CODE=10001" and "ONLINE=TRUE"`

[Additional sample queries](https://search.censys.io/search/examples?resource=hosts) 


## Threat Hunting / Investigative Blogs 🕵️
+ [Finding Hacked Webservers With Censys Search Data 🔎](https://censys.io/finding-hacked-web-servers-with-censys-search-data/)
+ [Tracking Deadbolt Ransomware Across the Globe](https://censys.io/tracking-deadbolt-ransomware-across-the-globe/)
+ [Where the Weird Things Are 🛸 Investigating Unusual Internet Artifacts with Censys Search Data](https://censys.io/where-the-weird-things-are-%f0%9f%9b%b8-investigating-unusual-internet-artifacts-with-censys-search-data/)



## Threat Tracking Dashboards 👁‍🗨
The Censys Research team has published several dashboards to track vulnerabilities (or software that's seen several recent vulnerabilities) over time. 

+ [Confluence dashboard](https://datastudio.google.com/s/pZ2tJrlKVrM)
+ [Deadbolt ransomware dashboard](https://datastudio.google.com/s/l58W0sXWv2Q)