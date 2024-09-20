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

# Examples

*Investigate the mx-1.pcap file with the default configuration file*
- sudo snort -c /etc/snort/snort.conf -A full -l . -r mx-1.pcap


# Writing IDS Rules (FTP)
*Write a single rule to detect "all TCP port 21" traffic in the given pcap*
- Rule: 
  - alert tcp any 21 <> any any (msg:"Outbound ftp traffic detected";sid:1000000000003; rev :1)
  - alert tcp any any <> any 21 (msg:"Inbound ftp traffic detected";sid:1000000000004; rev :1)
 
*What is the FTP service name?*
- sudo strings snort.log.file_name | grep 220 | head
- code 220 signifies a successful response that indicates the FTP server

*Write a rule to detect failed FTP login attemps in the given pcap*
- alert tcp any any <> any 21 (msg:"Failed ftp login attempt";content:"530";sid:1000000000005; rev :1)
- “530” is the FTP code that denotes unsuccessful FTP login attempts.

*Write a rule to detect successful FTP logins in the given pcap*
- alert tcp any any <> any 21 (msg:"Successful ftp login";content:"230";sid:1000000000006; rev :1)

*Write a rule to detect FTP login attempts with the "Administrator" username but no password entered yet*
- alert tcp any any <> any 21 (msg:"Invalid Admin Password";content:"331";content:"Administrator";sid:1000000000008; rev :1)

# Writing IDS Rules(PNG)

*Write a rule to detect the PNG file in the given pcap*
- alert tcp any any -> any any (msg:"PNG File Detected"; content:"|89 50 4E 47 0D 0A 1A 0A|"; depth:8;sid:10000000009)
- sudo strings ftp-png-gif.pcap

Write a rule to detct the GIF file in the given pcap*
- alert tcp any any -> any any (msg:"GIF File Detected"; content:"GIF89a"; depth:6;sid:10000000010)
- sudo strings snort.log.file_name

# Writing IDS Rules (Torrent Metafile)

*Write a rule to detect the torrent metafile in the given pcap*
- alert tcp any any -> any any (msg:"Torrent File Detected"; content:".torrent"; nocase;sid:10000000011)

*What is the name of the torrent application*
- sudo strings snort.log.file_name

# Troubleshooting Rule Syntax Erros

# Challenges
***Scenario 1 | Brute-Force***
- Step 1: Run Snort in sniffer mode
  - sudo snort -v -l .
- Step 2: Read log file
  - sudo snort -r snort.log.file_name -X
- Step 3: Use grep to track common port being used
  - sudo snort -r snort.log.file_name -X | grep :22
- Step 4: Write rule
  - drop tcp any 22 <> any any (msg:"SSH Connection attempted"; sid:100001; rev:1;)
- Step 5: Run rule to stop attack
  - sudo snort -c /etc/snort/snort.conf -q -Q --daq afpacket -i eth0:eht1 -A full
 
***Scenario 2 | Reverse Shell Attack***
- Step 1: Run Snort in Sniffer Mode
  - Use sudo snort -v -l .
- Step 2: Inspect the Log File
  - Use sudo snort -r snort.log.<log_number> -X / sudo snort -r snort.log.<log_number> -X | grep :4444 
- Step 3: Analyze Packet Details: Limit the number of results by running
  - sudo snort -r snort.log.<log_number> -X -n 10 
- Step 4: Write a Snort Rule: Open the local.rules file using sudo gedit /etc/snort/rules/local.rules.
  - drop tcp any 4444 <> any any (msg:"Reverse Shell Detected"; sid:100001; rev:1;).
- Step 5: Run Snort in IPS Mode: Execute Snort in IPS mode using
  - sudo snort -c /etc/snort/snort.conf -q -Q --daq afpacket -i eth0:eth1 -A full 







