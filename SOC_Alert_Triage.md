								                                -: SOC Alert Triage – Complete Guide :- 

What is Alert Triage?
Alert triage is the process of reviewing, validating, and prioritizing security alerts to decide if they represent a true security incident.

Goal :-
* Identify true positives quickly
* Filter out false positives
* Prioritize incidents based on severity

Why Triage is Important
Reasons :-
* Reduces false-positive alerts
* Ensures high-severity incidents get attention
* Improves SOC efficiency
* Builds context for faster response
If triage is done wrong, you'll waste hours chasing false positives or worse, miss a real attack.

Types of Alerts :-
Alert Type	    Example	                    Common Source
Authentication	    Failed logins, brute force	    Windows, EDR
Network	            Suspicious outbound traffic	    Firewall, IDS
Endpoint	    Malware execution	            EDR, AV
Email	            Phishing attempts	            Email Gateway
Cloud	            Suspicious IAM changes	    AWS, Azure logs
* Based on type of alert, approach will be deside. 1st step is to understand about alert and its source.

SOC Alert Flow :-
Detection → Alert Generated → SIEM → Analyst Triage → True/False Positive → Escalation

5-Step Triage Process
1. Identify Alert Context (Source, Device, User, Time)
2. Gather Evidence (logs, artifacts, user history)
3. Validate Alert (real or false?)
4. Determine Severity (impact, scope, criticality)
5. Escalate or Close (ticket with detailed notes)

1 – Identify the Context-
* Where did this alert originate? (Firewall, EDR, SIEM)
* Who or what is impacted?
* Is this asset critical?
* Always start with why, who, where & how.

2 – Gather Evidence -
* Collete evidence from all sources
* IEM logs (Splunk, Wazuh, Sentinel)
* Endpoint logs (Sysmon, EDR)
* Threat intel platforms (VirusTotal, OTX)
* User/Host details (AD, CMDB)
* Collect logs and add extra information like (user info, location, past activity) to get detail orverview of the incident.

3 – Validate the Alert -
Check for:
* Is this normal and safe activity?
* Does it match any known attack signs (bad IP, domain, file)?
* Is the user doing what they usually do?

4 – Determine Severity -
Severity   Description	             Example
High	   Active compromise	     Malware execution
Medium	   Suspicious but contained  Phishing email
Low	   Informational	     Failed logon attempt
*Categorize incidents before esclate to next level.

5 – Escalate or Close -
* True Positive: Escalate with full context
* False Positive: Close with justification
* Incomplete Info: Gather more data and monitor
*Alwasy esclate  alert with complete notes which are find.



 


