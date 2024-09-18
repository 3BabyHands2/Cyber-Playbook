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

***Logger Mode***
- "-l": Logger mode, target log and alert output directory. Default output folder is /var/log/snort | Default action is to dump as tcpdump format in /var/log/snort
- "-K ASCII": Log packets in ASCII format
- "-r": Reading option, read the dumpbed logs in Snort
- "-n": Specify the number of packets that will process/read

*Filter Binary Log Files*
- sudo snort -r logname.log -X
- sudo snort -r logname.log icmp
- sudo snort -r logname.log tcp
- sudo snort -r logname.log 'udp and port ?'
- sudo snort -r logname.log 'tcp and port ?'

***Snort in IDS/IPS Mode***
- -c	
Defining the configuration file.

- T	Testing the configuration file.
- N	Disable logging.
- D	Background mode.
- A	Alert modes;

  - full: Full alert mode, providing all possible information about the alert. This one also is the default mode; once you use -A and don't specify any mode, snort uses this mode.
fast:
  - Fast mode shows the alert message, timestamp, source and destination IP, along with port numbers.

  - console: Provides fast style alerts on the console screen.

  - cmg: CMG style, basic header details with payload in hex and text format.

  - none: Disabling alerting.
 
***PCAP Investigation***
- -r / --pcap-single= :	Read a single pcap
- --pcap-list="" :	Read pcaps provided in command (space separated).
- --pcap-show	: Show pcap name on console during processing.

*Example: Investigate the mx-1.pcap file with the default configuration file*
- sudo snort -c /etc/snort/snort.conf -A full -l . -r mx-1.pcap


