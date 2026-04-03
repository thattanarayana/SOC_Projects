                            -: Privilege Escalation Monitoring using Loggly :-
Scenario -
-> This lab simulates a privilege escalation attempt, where a normal user tries to gain administrative (root) access on a Linux system. 
-> The objective is to monitor and detect such activities using Loggly.

Privilege Escalation Activity -
-> The following commands were executed on the Linux machine to simulate escalation attempts
* sudo ls
* sudo apt update
* sudo su
* sudo -l
* sudo -i
* sudo cat /etc/shadow
* sudo -k
* su & su root (Enter the worng passord)

Log Detection in Loggly -
  -> To identify suspicious privilege escalation behavior, the following search queries were used:
* syslog.appName:su
* syslog.appName:authentication Fail

Analysis Performed for below activity -
-> User Activity – Identified which user executed privileged commands
-> Frequency – Multiple sudo and failed authentication attempts
-> Time Analysis – Detection of unusual or non-working hour activity
-> Sensitive Access – Attempts to read restricted files like /etc/shadow
-> Abnormal Behavior – Execution of SUID binaries and PATH hijacking

Below points identified on the activity -
-> Repeated failed sudo or su attempts indicate possible brute-force attack
-> Unauthorized access to sensitive files suggests credential harvesting attempts
-> Execution of SUID binaries can lead to privilege escalation exploitation
-> PATH manipulation indicates command hijacking attack
-> Sudden root access sessions should be flagged for investigation

Privilege-escalation Alert Configuration (Loggly) -
-> Implemented a real-time alerting mechanism in Loggly to detect potential privilege-escalation attack 
-> Configured alert to trigger email notifications when
-> Invalid SU root login or multipule root login attempts 
-> The alert condition is evaluated every 5 minute, enabling quick detection of suspicious activity 
-> Reference screenshot attached under labs folder: privilege-escalation_3.png

Note :- 
-> Capture images attached under the labs folder for eveidence purpose.   
-> Images are in the name of "privilege-escalation_1, privilege-escalation_2".
