# Cyber Defense Framework

***Hash Values***
- MD5 (Message Digest): Cryptographic hash function with a 128-bit hash value (NOT cryptographically secure)
- SHA-1 (Secure Hash Algorithm 1) : When data is fed to SHA-1 Hashing Algorithm, SHA-1 takes an input and produces a 160-bit hash value string as a 40 digit hexadecimal number. (Susceptible to brute-force attacks)
- SHA-2 (Secure Hash Algorithm 2) : Designed to replace SHA-1 - Has Many variants = SHA-256 (returns a hash value of 256-bits as a 64 digit hexadecimal number)
# 
 - A hash is not considered to be cryptographically secure if two files have the same hash value or digest.
 - Security professionals usually use the hash values to gain insight into a specific malware sample, a malicious or a suspicious file, and as a way to uniquely identify and reference the malicious artifact.

*Hash lookup Tools*
- https://www.virustotal.com/gui/
- https://metadefender.opswat.com/?lang=en

***IP Address***
- A common defense tactic is to block, drop, or deny inbound requests from IP addresses on your parameter or external firewall.
    - This tactic is often not bulletproof as it’s trivial for an experienced adversary to recover simply by using a new public IP address.
- One of the ways an adversary can make it challenging to successfully carry out IP blocking is by using Fast Flux.
    - DNS technique used by botnets to hide phishing, web proxying, malware delivery, and malware communication activities behind compromised hosts acting as proxies.
- https://unit42.paloaltonetworks.com/fast-flux-101/

***Domain Names***
- Domain Names can be a little more of a pain for the attacker to change as they would most likely need to purchase the domain, register it and modify DNS records.
- Many DNS providers have loose standards and provide APIs to make it even easier for the attacker to change the domain.
#
*Legit DNS*
![image](https://github.com/user-attachments/assets/9cfe6120-2987-4e1d-99c5-b72e531d4151)
#
*Malicious DNS*
![image](https://github.com/user-attachments/assets/da6f8fc0-b345-4bc9-9c12-e41044f564a1)

*Punycode Attack*
- Punycode is a way of converting words that cannot be written in ASCII, into a Unicode ASCII encoding
- What you saw in the URL above is adıdas.de which has the Punycode of http://xn--addas-o4a.de/

*URL Shortener*
- Tool that creates a short and unique URL that will redirect to the specific website specified during the initial step of setting up the URL Shortener link.
- bit.ly
- goo.gl
- ow.ly
- s.id
- smarturl.it
- tiny.pl
- tinyurl.com
- x.co

***Host Artifacts***
- Host artifacts are the traces or observables that attackers leave on the system, such as registry values, suspicious process execution, attack patterns or IOCs (Indicators of Compromise), files dropped by malicious applications, or anything exclusive to the current threat.

***Network Artifacts***
- A network artifact can be a user-agent string, C2 information, or URI patterns followed by the HTTP POST requests.
- Can be detected in Wireshark PCAPs using network protocol analyzer:
  - Tshark
  - Snort (IDS logging)

***Tools***
- Attackers would use the utilities to create malicious macro documents (maldocs) for spearphishing attempts, a backdoor that can be used to establish C2 (Command and Control Infrastructure), any custom .EXE, and .DLL files, payloads, or password crackers.
- 

