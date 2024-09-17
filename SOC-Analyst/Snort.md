# Snort

***Commands***
- Instance version: snort -V
- Ensure configuration file is valid: sudo snort -c /etc/snort/snort.conf -T
  - "-T" is used for testing configuration file | "-c" is identifying the configuration file | "-V' provides information about the instance version

***Sniffer Mode***
-  "-v": Verbose. Display the TCP/IP output in the console.
- "-d": Display the packet data (payload).
- "-e": Display the link-layer (TCP/IP/UDP/ICMP) headers. 
- "-X":	Display the full packet details in HEX.
- "-i":	This parameter helps to define a specific network interface to listen/sniff. Once you have multiple interfaces, you can choose a specific interface to sniff.  

*Sniffing with parameter "-i"*
- sudo snort -v -i eth0

*Sniffing with parameter "-v"*
- sudo snort -v

*Sniffing with parameter "-d"*
- sudo snort -d

*Sniffing with parameter "-de"*
- snort -d -e

*Sniffing with parameter "-X"*
- sudo snort -X
