# Threat Intelligence Tools

***UrlScan.io***
https://urlscan.io/
- Used to automate the process of browsing and crawling through websites to record activities and interactions
- Scan Results:
  - Summary: Provides general information about the URL, ranging from the identified IP address, domain registration details, page history and a screenshot of the site.
  - HTTP: Provides information on the HTTP connections made by the scanner to the site, with details about the data fetched and the file types received.
  - Redirects: Shows information on any identified HTTP and client-side redirects on the site.
  - Links: Shows all the identified links outgoing from the site's homepage.
  - Behaviour: Provides details of the variables and cookies found on the site. These may be useful in identifying the frameworks used in developing the site.
  - Indicators: Lists all IPs, domains and hashes associated with the site. These indicators do not imply malicious activity related to the site.
 
***Abuse.ch***
https://abuse.ch/
- Identify and track malware and botnets through these platforms:
  - Malware Bazaar:  A resource for sharing malware samples.
  - Feodo Tracker:  A resource used to track botnet command and control (C2) infrastructure linked with Emotet, Dridex and TrickBot.
  - SSL Blacklist:  A resource for collecting and providing a blocklist for malicious SSL certificates and JA3/JA3s fingerprints.
  - URL Haus:  A resource for sharing malware distribution sites.
  - Threat Fox:  A resource for sharing indicators of compromise (IOCs).
 
*MalwareBazaar*
https://bazaar.abuse.ch/
- Malware Samples Upload: Security analysts can upload their malware samples for analysis and build the intelligence database. This can be done through the browser or an API.
- Malware Hunting: Hunting for malware samples is possible through setting up alerts to match various elements such as tags, signatures, YARA rules, ClamAV signatures and vendor detection.

*FeodoTracker*
https://feodotracker.abuse.ch/
- Share intelligence on botnet Command & Control (C&C) servers associated with:
  - Dridex
  - Emotes (aka Heodo)
  - TrickBot
  - QakBot
  - BazarLoader/BazarBackdoor
- Additionally provides:
  - IP blocklists and mitigation information (prevent botnet infections)
  - IOC blocklists and mitigation information (prevent botnet infections)
 
*SSL Blacklist*
https://sslbl.abuse.ch/
- Tool to identify and detect malicious SSL connections
- Denylist is also used to identify JA3 fingerprints that would help detect and block malware botnet C2 communications on the TCP layer

*URLhaus*
https://urlhaus.abuse.ch/
- Tool focuses on sharing malicious URLs used for malware distribution
- Database for domains, URLs, hashes and filetypes
- Provides feeds associated with country, AS number and Top Level Domain

*ThreatFox*
https://threatfox.abuse.ch/
- Search for, share and export indicators of compromise associated with malware

***PhishTool***
https://www.phishtool.com/
- 

***Cisco Talos Intelligence***
https://talosintelligence.com/
- 

