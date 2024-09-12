# Cyber Kill Chain
- The framework defines the steps used by adversaries or malicious actors in cyberspace.
- An adversary needs to go through all phases of the Kill Chain.
- The Cyber Kill Chain can be used to assess networks and system security by identifying missing security controls and closing certain security gaps based on company infrastructure.

***Reconnaissance***
- Reconnaissance is discovering and collecting information on the system and the victim.
- The reconnaissance phase is the planning phase for the adversaries.
- OSINT falls uder reconnaissance.
  - First step an attacker needs to complete to carry out further phases of an attack.
#
*Email Harvesting Tools*
- https://github.com/laramies/theHarvester
- https://hunter.io/
- https://osintframework.com/

***Weaponization***
- Create an infected Microsoft Office document containing a malicious macro or VBA (Visual Basic for Applications) scripts. If you want to learn about macro and VBA, please refer to the article "Intro to Macros and VBA For Script Kiddies" by TrustedSec.
- An attacker can create a malicious payload or a very sophisticated worm, implant it on the USB drives, and then distribute them in public. An example of the virus. 
- An attacker would choose Command and Control (C2) techniques for executing the commands on the victim's machine or deliver more payloads. You can read more about the C2 techniques on MITRE ATT&CK.
- An attacker would select a backdoor implant (the way to access the computer system, which includes bypassing the security mechanisms).
#
*Terminology*
- Malware: program or software that is designed to damage, disrupt, or gain unauthorized access to a computer
- Exploit: program or code that takes advantage of the vulnerability or flaw in the application or system
- Paylod: malicious code that the attacker runs on the system

***Delivery***
- The Delivery phase is when to choose the method for transmitting the payload or the malware:
  - Phishing email
  - Distributing infected USB drives
  - Watering hole attack

***Exploitation***
- To gain access to the system, an attacker needs to exploit the vulnerability:
  - The victim triggers the exploit by opening the email attachment or clicking on a malicious link.
  - Using a zero-day exploit.
  - Exploit software, hardware, or even human vulnerabilities. 
  - An attacker triggers the exploit for server-based vulnerabilities.
 
***Installation***
- Attacker needs to install persistent backdoor so that they may access it at a later time
- Persistence can be achieved through:
  - Installing a web shell (malicious script) on the webserver
  - Meterpreter can install a backdoor on victim's machine
  - Use Timestomping technique to avoid detection

***Command & Control***
- After getting persistence, attacker will open up C2(Command and Control)
- Common C2 channels:
  - The protocols HTTP on port 80 and HTTPS on port 443 - this type of beaconing blends the malicious traffic with the legitimate traffic and can help the attacker evade firewalls.  
  - DNS (Domain Name Server). The infected machine makes constant DNS requests to the DNS server that belongs to an attacker, this type of C2 communication is also known as DNS Tunneling.
- Important to note that an adversary or another compromised host can be the owner of the C2 infrastructure

***Exfiltration***
- After going through the six phases of the attack, the attacker can now achieve the following: 
  - Collect the credentials from users.
  - Perform privilege escalation (gaining elevated access like domain administrator access from a workstation by exploiting the misconfiguration).
  - Internal reconnaissance (for example, an attacker gets to interact with internal software to find its vulnerabilities).
  - Lateral movement through the company's environment.
  - Collect and exfiltrate sensitive data.
  - Deleting the backups and shadow copies. Shadow Copy is a Microsoft technology that can create backup copies, snapshots of computer files, or volumes. 
  - Overwrite or corrupt data.

- exploit public-facing application: Adversaries may attempt to exploit a weakness in an Internet-facing host or system to initially access a network. The weakness in the system can be a software bug, a temporary glitch, or a misconfiguration
- data from local system: 
- powershell:
- dynamic linker hijacking: adversaries can execute malicious code by hijacking environment variables used by the dynamic linker to load shared libraries. See examples, tactics, platforms, and mitigations for this technique.
- spearphishing attachment: dversaries may send spearphishing emails with a malicious attachment in an attempt to gain access to victim systems. Spearphishing attachment is a specific variant of spearphishing. Spearphishing attachment is different from other forms of spearphishing in that it employs the use of malware attached to an email.
- fallback channels: maintain reliable command and control and avoid data transfer thresholds.


