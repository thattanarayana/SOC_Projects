								                                 -: Incident Response (IR) – SOC Analyst Guide :- 
								
What is Incident Response (IR)?
Incident Response (IR) is a structured process used by SOC teams:
* Detect
* Analyze
* Contain
* Eradicate
* Recover 
from cybersecurity incidents.

Objective:
* Minimize damage
* Reduce recovery time
* Prevent future incidents
Note :- Incident Response is not about panic — it's about process. It's how a SOC team turns chaos into clarity.

SOC Levels Overview
SOC Tier	                   Responsibilities
L1 (Monitoring & Triage)	Monitor alerts, validate incidents
L2 (Investigation & Analysis)	Deep dive analysis, correlation
L3 (Threat Hunting / IR)	Handle major incidents, malware, threat intelligence
Note :- L1 analysts are the first responders. You're the eyes and ears of the SOC.

SOC L1 Key Responsibilities :-
* Continuous alert monitoring
* Alert triage & initial validation
* Incident categorization (False Positive, True Positive)
* Escalation to L2/L3 when required
* Documentation & ticket creation
Important :- As an L1, your job is not to fix everything — it's to detect fast, verify, and escalate accurately.

The Incident Response Lifecycle :- Based on NIST SP 800-61:
* Preparation
* Detection & Analysis
* Containment
* Eradication
* Recovery
* Post-Incident Activities
Note :- This is the industry-standard framework followed by all organizations.

-> Stage 1 – Preparation
* Goal: Build readiness for potential incidents
Includes :-
* Create IR policy & playbooks
* Configure SIEM rules
* Set up communication plans
* Train analysts
Key Idea :- Preparation ensures defenses, tools, and teams are ready before an attack happens.

-> Stage 2 – Detection & Analysis
* Goal: Identify suspicious activity & verify if it’s an incident
Data Sources :-
* SIEM alerts
* Endpoint logs (Windows, Sysmon, EDR)
* Firewall/Proxy logs
* Threat Intelligence
Note :- This is where SOC L1 spends most time — monitoring alerts, verifying logs, and confirming if it's real.

Incident Classification
Incident Type	                  Example
Malware Infection	     Suspicious process detected
Phishing Attack	             Malicious email link
Data Exfiltration	     Outbound traffic spike
Unauthorized Access	     Login from unusual IP
Policy Violation	     Unapproved software detected
Purpose :- Helps determine what kind of threat you're dealing with.

-> Stage 3 – Containment
* Objective: Limit the spread of the attack
L1 Tasks :-
* Disable affected user account
* Isolate endpoint (via EDR)
* Block malicious IP/domain in firewall
* Notify L2/L3 team
Key Idea :- Containment is like sealing a leak — stopping damage from spreading.

-> Stage 4 – Eradication
* Objective: Remove the threat completely
Examples :-
* Remove malware/backdoor
* Delete malicious registry keys
* Patch vulnerabilities
* Reset credentials
Note :- Mostly handled by L2/L3, but L1 provides initial evidence.

-> Stage 5 – Recovery
* Objective: Restore normal business operations safely
Tasks :-
* Reconnect isolated systems
* Reinstall clean OS/images
* Monitor for re-infection
* Validate system functionality
Key Idea :- Recovery is not just restarting systems — it's ensuring they are clean.

-> Stage 6 – Post-Incident Review
* Objective: Learn from the incident
Activities :-
* Conduct Root Cause Analysis (RCA)
* Update playbooks & detection rules
* Share IOCs with TI team
* Prepare lessons-learned report
Important :- Every incident should improve your SOC maturity.

-> SOC Workflow Visualization
Flow :-
* Alert → Triage → Validation → Escalation → RCA → Containment  → Closure
Note :- This is the daily workflow of an L1 analyst — from detection to closure.

-> Incident Ticketing Workflow
Ticket Elements :-
* Alert Source (SIEM, EDR, Firewall)
* Description of event
* Timestamps
* Impacted Host/User
* Action Taken
* Escalation Reference
Important :- Proper ticketing is critical — logs and tickets are evidence in audits/investigations.

-> Example IR Playbook – Phishing Email
L1 Steps :-
* Analyze reported email header
* Extract IOCs → validate via VirusTotal
* Search SIEM for same domain/IP
* Block malicious indicators
* Escalate with findings
Note :- Playbooks are SOPs — follow them step-by-step during incidents.

-> Common Challenges in IR
* High volume of false positives
* Delayed detection
* Lack of context or enrichment
* Poor documentation
* No standardized playbooks
Goal of SOC Maturity :- Reduce false positives and improve response speed.


