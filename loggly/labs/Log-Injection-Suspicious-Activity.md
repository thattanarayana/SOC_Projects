				          	-: Log Injection & Suspicious Activity Detection :-

Overview -
-> Simulated log injection and suspicious activity scenarios on a Linux system to understand how attackers generate misleading or malicious logs.
-> Configured Loggly to detect, filter, and alert on such events in real time.

Attack Simulation (Log Injection) -
-> Generated custom suspicious log entries using the Linux logger utility to mimic attacker behavior:
-> logger "ALERT: multiple failed login attempts detected from 192.168.1.10"
-> logger "WARNING: suspicious process execution"

Log Analysis in Loggly -
-> Filter Applied: syslog.appName:narayana
-> Search Query: ALERT OR WARNING

Alert Configuration -
-> Configured real-time alerts in Loggly based on suspicious log patterns:
-> Trigger condition: Presence of "ALERT" or "WARNING" keywords
-> Monitoring interval: Continuous / near real-time
-> Notification: Alert triggered when suspicious logs are detected
