								                  -: Wireshark for SOC Analysts :-

What is Wireshark?
Wireshark is a network traffic analysis tool used to capture and inspect packets in real time. It enables analysts to monitor 
network communications, investigate security incidents, and troubleshoot network-related issues.

Using wireshark below activites can be pefromed -
* See raw network data
* Understand 1000+ protocols (like HTTP, DNS, etc.)
* Check packet header details 
* Find suspicious activity
* Fix network problems

Why SOC Analysts Use Wireshark?
SOC (Security Operations Center) analysts use Wireshark to investigate security issues.
Use cases -
* Check suspicious network connections
* Analyze malware communication (C2 traffic)
* Investigate DNS queries
* Detect data theft (exfiltration)
* Validate alerts from IDS/IPS
* Understand how protocols behave
* Simple difference SIEM and Wireshark (SIEM → shows logs) (Wireshark → shows actual raw traffic)

                                         -: Packet Capture Basics :-

What is a Packet?
A packet is a small piece of data sent over a network. Instead sending entire data into file it divide data in to no of 
packets 

Packet contains -
* Header → information about sender/receiver
* Metadata → extra info
* Payload → actual data

Packet Structure -
-> Header (Ethernet Header (Layer 2), Source MAC & Destination MAC)
-> Metadata [IP Header (Layer 3) {Source IP, Destination IP, TTL & Protocol}]
            [TCP/UDP Header (Layer 4) {Source Port, Destination Port & Flags}]
-> Payload (Actual data (web page, file, message, etc.))

What is PCAP?
* PCAP stands for Packet Capture, is an application programming interface (API) used for capturing network traffic. It is a  
  widely used file format that stores data captured from network traffic, providing essential tools for network analysis, 
  troubleshooting, and security investigations

PCAP Files (SOC View) -
PCAP contains -
* Time
* Source & destination IP
* Ports
* Protocol
* Payload
* File size - Few MB → several GB

How Wireshark Works?
Wireshark does NOT create traffic it only listens (passive tool)
Internally:
* Captures data from network interface
* Uses libraries like libpcap / WinPcap
* Breaks data into protocols
* Shows packets in layers

OSI & TCP/IP Model (Important) -
Wireshark shows data in layers
* Layer 2 → MAC, ARP
* Layer 3 → IP
* Layer 4 → TCP / UDP
* Layer 5–7 → HTTP, DNS, SSL

Wireshark Interface (UI) -
Main parts -
These main part of the wireshaer UI dashboard
* Packet List → all packets
* Packet Details → full breakdown
* Packet Bytes → raw data
* Filter bar → search packets
* Statistics → analysis tools
* Capture window → choose network

What is a Capture?
A capture is the process of recording network packets flowing through an interface.
using buttons start, Double-click eth0, stop, restart buttons we can perform the operations


Differecne between Capture Filters and Display Filters ?
Capture Filters -
Decide what to capture

Display Filters
Decide what to show


Some Important Protocols - 
You must know these as begginer-
* ARP
* DNS
* HTTP / HTTPS
* TCP
* UDP
These make up maximum of traffic you will see.

TCP Handshake & Flags - 
3-Way Handshake -
* SYN → Start connection
* SYN-ACK → Response
* ACK → Confirm

Important Flags -
* SYN
* ACK
* FIN
* RST
* PSH

How to identify Suspicious Traffic ?
* Too many DNS requests
* Unknown external IP connections
* Repeated SYN packets (scan/DoS)
* Strange HTTP requests
* TLS errors
* Large data uploads
* Regular patterns (beaconing)

Wireshark in SOC investigation to find some activites -
* Phishing detection
* Malware communication detection
* Data theft detection
* PowerShell download analysis
* IDS/IPS alert validation
* VPN traffic analysis
* Detect brute-force or scanning

Activittes not to do -
* Don’t capture on production servers
* Don’t run as admin unnecessarily
* Don’t capture without permission
* Don’t share PCAPs carelessly
* Because it may contains (Passwords, Tokens, Personal data)

Basic Filters -
* ip → all IP traffic
* tcp → TCP packets
* udp → UDP packets
* http → HTTP traffic
* dns → DNS traffic
* tls → encrypted traffic

SOC Workflow Using Wireshark -
Steps -
* SIEM alert comes
* Analyst gets PCAP
* Apply filters
* Check anomalies
* Add findings to ticket
* Escalate if needed

Using wireshark SOC analyst work make but it doesn't replace SIEM.


