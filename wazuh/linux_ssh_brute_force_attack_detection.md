			                          -: Linux SSH Brute Force Attack Detection using Wazuh Cloud SIEM :-

Project Overview -
This project demonstrates how to simulate and detect a Linux SSH brute force attack using Wazuh Cloud SIEM in a real-world SOC lab environment.
The objective of this lab is to understand -
* How attackers perform credential-based attacks
* How security events are generated during authentication attacks
* How SOC analysts detect, investigate, and validate incidents using a SIEM platform
* This hands-on project focuses on attack simulation, threat hunting, alert investigation, and incident validation using Wazuh Cloud.

Project Objectives - 
* Simulate SSH brute force attacks from Kali Linux
* Generate failed authentication events
* Detect suspicious login activities in Wazuh Cloud SIEM
* Monitor successful and failed login attempts
* Perform threat hunting and alert investigation
* Understand SOC analyst workflows and incident validation

Lab Environment - 
Component			              Purpose
Physical Laptop		      Access Wazuh Cloud Dashboard
Kali Linux VM		        Attacker Machine
Windows VM			        Victim / Endpoint System
OpenSSH Server		      Target Service
Wazuh Agent			        Endpoint Monitoring & Log Collection

Tools & Technologies Used - 
-> Wazuh Cloud SIEM
-> Kali Linux
-> Hydra
-> OpenSSH
-> Windows Event Logs
-> Threat Hunting
-> Security Event Analysis

SSH Brute Force Attack Simulation/ steps -
Step 1 — Get target IP address
         Open command prompt on the windows machine and run cmd = ipconfig
	       Copy the IPv4 address of the target system.
Step 2 — Perform brute force attack from Kali Linux
	       Open terminal in Kali Linux and run cmd = hydra -l yash -P password.txt ssh://192.168.200.128 
Step 3 — Manual ssh login attempt
	       Run the cmd = ssh yash@192.168.200.128

Windows Failed Login Simulation -
* Generate failed login events
* Start the windows VM
* Enter incorrect passwords multiple times
* Windows will generate authentication failure events
* These logs are collected by the Wazuh agent and forwarded to the SIEM dashboard.

Monitoring Alerts in Wazuh Cloud - 
Navigate to -> Threat Hunting → Events -> Monitor alerts related to -
* Authentication failures
* Authentication successes
* SSH login attempts
* Brute force attack activity
* Suspicious login behavior

Creating Custom Detection Rules in Wazuh -
* Navigate to: Menu → Server Management → Rules
* Steps -> Click Add New Rule File -> Enter rule name -> Add custom detection rule -> Save the rule

Event Investigation Process -
* Filter specific events navigate to Threat Hunting → Events → Add Filter Select (Field Name, Operator & Value) -> Then click Save.

Inspect Event Details / investigate alerts -
* Events -> Select Event -> Inspect Document Details
* Review these (Source IP, Username, Event ID, Login status, Timestamp & Attack pattern)

SOC Investigation & Threat Hunting -
During investigation check the below parametres 
* Identify suspicious IP addresses
* Detect repeated failed logins
* Confirm successful compromise attempts
* Differentiate true positives from false positives
* Analyze attacker behavior patterns

Project Outcome - 
By completing this project, I gained practical experience in -
* SSH brute force attack simulation
* Authentication attack detection
* Wazuh SIEM monitoring
* Threat hunting techniques
* Security event analysis
* Incident investigation workflows
* SOC operations and alert triage
* Custom Wazuh rule creation

Skills & Knowledge Gained - 
* SIEM Monitoring
* Threat Hunting
* Security Event Analysis
* SSH Attack Detection
* Windows Log Analysis
* Wazuh Rule Creation
* Incident Investigation
* SOC Operations
* Authentication Security Monitoring

Learning Outcome - 
This project provided hands-on experience in:
* Blue Team operations
* SOC analyst workflow
* Security monitoring and alert triage
* Real-world attack simulation and detection
It helped strengthen practical cybersecurity and defensive security skills using a real SIEM environment.

Note :- 
