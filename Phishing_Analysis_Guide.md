						-: Phishing Analysis Guide for SOC Analysts :-

What is Phishing?

A social engineering attack that tricks users into revealing credentials, clicking malicious links, or downloading attachments.

Common Types :-
* Credential Harvesting
* Malware Delivery
* Business Email Compromise (BEC)
* Spear Phishing
* Whaling

Why SOC Analysts Study Phishing?
As a SOC Analyst, you must :-
* Identify phishing attempts early
* Investigate reported suspicious emails
* Analyze email headers & links
* Extract IOCs (IPs, URLs, hashes)
* Correlate indicators in SIEM

Anatomy of a Phishing Email
Key Components :-
* Sender address
* Subject line
* Email body
* Embedded links
* Attachments
* Email headers

The Email Header – Analyst’s Goldmine
Key Header Fields to Analyze :-
-> Return-Path: Actual Sender’s Email
-> Received: Show Mail Reply Path
-> Message-ID: Origin Mail Server
-> Reply-To: Redirection Trick
-> From: Visible Sender
-> SPF/DMARC/DKIM: Authentication Results

How to View Email Headers?
Always extract the raw header text, it’s the foundation for your analysis.

* Gmail: More → Show Original
* Outlook: File → Properties → Internet Headers

Analyzing Email Header
* Copy the email header from an Email :- 
* Open https://mxtoolbox.com/EmailHeaders.aspx
* Paste header → click “Analyze Header”
* Review hop details, IPs, delays

Authentication Mechanisms 
* SPF: Validates Sending IP → spf=fail
* DKIM: Validates Email Content Integrity → dkim=pass
* DMARC: Combines SPF & DKIM → dmarc=fail
If SPF or DKIM fails, there’s a 90% chance the email is spoofed.


Extracting IOCs from Email
IOC Types :-
* Malicious URLs
* Sender domain
* IPs from Received headers
* File hashes (attachments)

Phishing Campaign Indicators
Signs of a Large Campaign :-
* Multiple emails with same subject/template
* Identical URLs but different senders
* Repeated failed SPF/DKIM
* Multiple alerts in SIEM from same IP range

Mapping to MITRE ATT&CK :-
* Initial Access: Phishing → T1566
* Execution: User Execution → T1204
* Credential Access: Credential Phishing → T1566.002
* Collection: Email Collection → T1114
* Exfiltration: Exfiltration Over Web → T1567
Mapping phishing behavior to ATT&CK improves your SOC use case design and reporting.

Use Case in SIEM
Query Example :-
index=email_logs | search subject="password" OR subject="invoice"
| stats count by sender, subject, src_ip | where count > 5

Use Case – Detection Correlation
Combine Email Logs + Proxy Logs :-
* Extract URLs from email
* Search proxy/DNS logs for same domain
* Identify users who clicked links
This is how SOCs connect dots → from email to network → to confirm compromise.

Reporting Findings
Sample Phishing Report Sections :-
* Executive Summary
* Email Metadata
* IOC Table
* Analysis & Findings
* MITRE Mapping
* Recommendations
Documentation is key — every phishing analysis should result in a detailed, reusable report.

Mitigation & Prevention Steps
* Enable SPF, DKIM, and DMARC enforcement
* Use email sandboxing (e.g., Proofpoint, FortiMail)
* Implement domain whitelisting
* Train employees for phishing awareness
* Regularly update threat intelligence feeds
Technical controls help, but the best defense is awareness.


