     		                                -: Unauthorized Access Attempt on files, folders and operations :-

Overview -
-> As part of exploring the Loggly tool, I simulated multiple unauthorized access attempts and privilege escalation activities on a Linux system.
-> The objective was to generate real-time logs, analyze suspicious behavior, and configure alerts for detection.
 
 Activities Performed -
-> The following commands were executed to mimic unauthorized access to sensitive files, logs, and privileged operations:

# Access restricted directories and sensitive files
* cd /root
* cat /etc/shadow
* cat /etc/passwd
* cat /etc/hosts

# Attempt to read system and authentication logs
* cat /var/log/auth.log
* cat /var/log/syslog

# Simulate unauthorized user management actions
* adduser testuser
* passwd testuser
* usermod -aG sudo testuser
* deluser testuser

Alert Configuration in Loggly -
-> Created alerts to detect unauthorized file access and user activity
-> Configured conditions based on:
-> Access to restricted files
-> User account modifications
-> Privilege escalation commands
-> Alerts are triggered in near real-time based on defined thresholds
