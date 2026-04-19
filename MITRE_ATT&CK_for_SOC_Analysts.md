				                                                	-: MITRE ATT&CK for SOC Analysts :- 

What is MITRE ATT&CK?
-> Stands for Adversarial Tactics, Techniques & Common Knowledge
-> A knowledge base of real-world attacker behavior
-> Created by MITRE Corporation
-> Widely used in:
		SOC Operations
		Threat Hunting
		Red Teaming

Why MITRE ATT&CK for SOC?
-> Helps understand how attackers behave
-> Maps alerts/logs to attack techniques
-> Improves incident detection & response
-> Provides a common language across teams (SOC, Red Team, Management)

ATT&CK vs Cyber Kill Chain -
Cyber Kill Chain:
-> Linear (step-by-step attack stages)
-> High-level overview
MITRE ATT&CK:
-> Non-linear (real-world scenarios)
-> Detailed and practical
-> More useful for SOC analysts

ATT&CK Structure -
-> Tactics (WHY) → Attacker’s goal
-> Techniques (HOW) → Method used
-> Sub-techniques → Detailed actions
-> Detection → How to identify
-> Mitigation → How to prevent

ATT&CK Tactics - (Initial Access, Execution, Persistence, Privilege Escalation, Defense Evasion, Credential Access, Discovery, Lateral Movement, Collection, Command & Control, Exfiltration, Impact)

Initial Access -
-> Definition: Gaining entry into a system
-> Techniques (Phishing (T1566), Drive-by Compromise (T1189), Exploit Public-Facing Apps (T1190), 
Detection:
-> Monitor email logs
-> Monitor web traffic logs

Execution -
-> Definition: Running malicious code
-> Techniques(PowerShell (T1059.001), Command & Scripting Interpreter, Exploitation for Client Execution)
Detection:
-> Sysmon logs
-> Command-line monitoring

Persistence -
-> Definition: Maintaining access after reboot
-> Techniques:(Registry Run Keys (T1547.001), Scheduled Tasks (T1053), Service Creation (T1543))
Detection:
-> Autoruns monitoring
-> Task scheduler logs

ATT&CK for SOC Analysts -
-> Map alerts → ATT&CK techniques
-> Investigate incidents faster
-> Create detection rules

Examples:
-> Suspicious PowerShell → Execution (T1059)
-> RDP brute-force → Initial Access (T1110)

ATT&CK for Threat Hunting -
-> Use techniques as hypotheses
-> Perform proactive detection
Example:
-> Credential Dumping → Check LSASS access logs

ATT&CK in Real-World Tools -
-> SIEM Tools: (Splunk, IBM QRadar,Elastic Security, wazhu)
-> Map logs → ATT&CK techniques

EDR Tools -
-> Detect endpoint attacks using ATT&CK references
-> Threat Intelligence:
-> Map IOCs → ATT&CK TTPs
					  -: Common Attack Categories, Detection & Indicators :-
1. Brute Force Attack (Windows)
Definition: Repeated password guessing
Detection:
Windows Event Logs:
4625 → Failed login
4624 → Successful login
Indicators:
Multiple failed login attempts
Same IP address
Unusual login times

2. SSH Brute Force (Linux)
Definition: Password guessing on SSH (port 22)
Detection:
Check /var/log/auth.log
Indicators:
Repeated "Failed password" entries
Same IP trying multiple users
Sudden successful login

3. Phishing Attempts
Definition: Fake emails to steal credentials
Detection:
Email headers
Suspicious links
Indicators:
Unknown sender
Urgent language
Fake URLs

4. Malware Infections
Definition: Malicious software installed
Detection:
Antivirus alerts
Process monitoring
Indicators:
Unknown .exe files
High CPU/network usage
Suspicious outbound traffic

5. Privilege Escalation
Definition: Gaining higher access (user → admin)
Detection:
Privileged access logs
Indicators:
New admin accounts
Unauthorized privilege changes

6. Lateral Movement
Definition: Moving across systems in a network
Detection:
RDP logs
SMB logs
Indicators:
Same user on multiple systems
Unusual remote logins

7. Data Exfiltration
Definition: Stealing sensitive data
Detection:
Network monitoring
Indicators:
Large data transfers
Unknown external IP communication

8. Command & Control (C2)
Definition: Communication with attacker server
Detection:
DNS logs
Proxy logs
Indicators:
Repeated outbound traffic (beaconing)
Unknown domains

9. Suspicious PowerShell Activity
Definition: Malicious script execution
Detection:
Sysmon logs
Command-line logs
Indicators:
Encoded commands (-enc)
Hidden execution
Downloading scripts

10. Web Application Attacks
Examples:
SQL Injection
Cross-Site Scripting (XSS)
Detection:
Web server logs
WAF alerts
Indicators:
Strange URL inputs
Repeated requests
Malicious payloads
