#SOC Analyst learning process
SOC Log Monitoring & Attack Detection using Loggly

* As part of my SOC Analyst learning journey, I have explored studying Log Management cloud tool.
* I have also uploaded my complete project on Loggly, which includes detailed data and explanations of the concepts I learned.

-: Project Overview :-
* This project demonstrates how to build a SOC (Security Operations Center) monitoring system using Kali Linux and Loggly.
* Logs from Kali Linux are forwarded using rsyslog demo to Loggly, where they are analyzed to detect suspicious activities like brute force attacks, privilege escalation, and unauthorized access.

-: Architecture :-
* Kali Linux → rsyslog → Loggly → Dashboard & Alerts

 -: Tools Used :-
* Kali Linux
* Loggly (Cloud Log Management Tool)
* rsyslog
* Oracle VirtualBox
* Basic laptop

-: Expected outcome of the expirement :-
* Successfully configured centralized logging
* Forwarded Linux logs to Loggly
* Verified real-time log monitoring


				                                           -: Loggly Security Monitoring Lab :-

As part of exploring the Loggly log management tool, I created a dedicated labs folder containing hands-on security simulations and log analysis use cases. Each file demonstrates real-world attack scenarios and how they can be detected through log monitoring.

Lab Modules -

brute-force.md ->
Simulated brute-force attack attempts and analyzed authentication logs to identify repeated failed login patterns and intrusion indicators.

privilege-escalation.md ->
Demonstrated privilege escalation techniques including user switching, misuse of root access, and unauthorized admin-level operations, along with log-based detection strategies.

unauthorized-access.md ->
Simulated attempts to access restricted files and directories, highlighting how unauthorized access activities are recorded and monitored in logs.

Log-Injection-Suspicious-Activity.md ->
Generated custom suspicious log entries using system commands to mimic attacker behavior and explored methods to detect anomalies and injected logs.

Reconnaissance_Scanning_Behavior.md ->
Simulated reconnaissance activities such as network scanning and probing, and analyzed logs to identify early-stage attack patterns and vulnerability scanning behavior.

Key Points I have learned -
-> Hands-on simulation of real-world cybersecurity attack scenarios
-> Practical experience with log analysis and alert creation in Loggly
-> Strong understanding of threat detection using system logs
-> Focus on proactive monitoring and incident identification
