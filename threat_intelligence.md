								                                                    -: Threat Intelligence For SOC Analyst :-

-> What is Threat Intelligence?
   Threat Intelligence is a actionable knowledge which helps understand attackers pattern and steps.

-> Why Threat Intelligence is Important?
   It is make easy to understand the why attack is happened with these quesion who is attacking?, what they are doing?, why are they targetting us?, how do we defend?. 

-> Types of Threat Intelligence

   *Strategic Threat Intelligence - High level information about risks and trends. It doesn't look about code. It looks at 
    bussiness impact and security for long term.

   *Tactical Threat Intelligence - It explain about attacker TTP's (Tactic's, Techiqunes & Procedures) that attacker uses. It explain their style of action.

   *Operational Threat Intelligence - Informtion about ongoing attack. Who is attacking right now, which type of software & tricks they useing to perform the attack.

   * Techincal Threat Intelligence - It was the clues of or IOCs after the attack. It was raw data genrated by the systems.

-> Threat Intelligence Source of SOC Analyst -
   *Open-Source Intelligence (OSINT) – Publicly available data 
   *Commercial Intelligence – Paid threat feeds/services 
   *Internal Logs & Incident Data – Organization’s own security data 
   *Sharing Communities – Industry groups and threat-sharing platforms

-> Why SOC Needs Threat Intelligence
   *Enrich alerts with additional context
   *Detect known malicious IPs, domains, and infrastructure
   *Correlate alerts with ongoing incidents
   *Build strong detection use cases
   *Improve threat hunting capabilities

-> Threat Intelligence Lifecycle
   1. Planning – Define intelligence requirements
   2. Collection – Gather data from various sources
   3. Processing – Clean and organize the data
   4. Analysis – Convert data into actionable insights
   5. Dissemination – Share intelligence with teams
   6. Feedback – Improve based on outcomes

-> What is an IOC (Indicator of Compromise)?
   An IOC is evidence that indicates a system may have been compromised.
   Common IOCs include -
   *IP addresses
   *Domains / URLs
   *File hashes
   *Email headers and subjects
   *Registry changes

Practical Threat Intelligence (TI) — SOC Workflow
Scenario (Real-World Example)

SIEM (like Splunk or wazhu) generates an alert:

Multiple failed login attempts from IP: 185.234.219.12

-> Step 1: Collect IOC from Alert
   From the alert, extract -
   IP Address → 185.234.219.12
   Username targeted
   Timestamp
   This IP is your IOC (Indicator of Compromise)

-> Step 2: Check Threat Intelligence Sources
   Search this IP in public TI platforms -
   VirusTotal
   AbuseIPDB
   AlienVault OTX

  Example findings:
  Reported for brute-force attacks
  Country: Russia
  Reputation: Malicious

-> Step 3: Analyze (Add Context)
   Now you think like analyst:
   Is this IP attacking only 1 user or many?
   Is it part of a known attack campaign?
   Is it matching known TTPs (Brute Force attack)
   Conclusion -
   This is likely a credential brute-force attack

-> Step 4: Correlate in SIEM
   Search in your SIEM -
   Same IP in past logs?
   Other systems targeted?
   Any successful login?
   If yes → HIGH RISK 

-> Step 5: Take Action
   Block IP in firewall
   Disable or lock affected accounts
   Alert incident response team
   Create detection rule
 
-> Step 6: Create Detection Rule (Use Case)
   Example rule -
   IF failed login attempts > 10
   AND source IP is malicious (TI match)
   THEN trigger alert "Brute Force Attack"

-> Step 7: Feed Back to Threat Intelligence
   Add this IP to internal blacklist
   Share with team / community
   Improve future detection
