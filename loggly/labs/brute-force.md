                  -: LAB Brute Force Attack Detection using Loggly :-

__Objective of the projecct__
To simulate a brute force attack on a Linux system and detect it using centralized log monitoring in Loggly.                   

__Preffered Scenario__
An attacker attempts to gain unauthorized access by trying multiple passwords against a user account within a short time period.

Step 1: Brute Force Attack
->Execute the following command in Kali Linux: "for i in {1..50}; do ssh narayana@kali; done"
-> Attempts SSH login 50 times
-> Generates multiple failed authentication logs
-> It creates a brute force attack pattern

Step 2: Log Collection in Loggly
-> Ensure system logs are forwarded to Loggly via rsyslog.
-> Searched with the values "failed password or authentication failure or narayana"

Step 3: Log Analysis
-> Analyze the logs in Loggly dashboard:

Key Indicators:
-> Repeated login attempts for the same username (narayana)
-> High number of attempts in a short time window
-> Spike in event timeline
-> Same source IP (127.0.0.1 in this case)

 __Learnings of the project__
-> Understanding brute force attack patterns
-> Hands-on experience with SSH attack simulation
-> Log analysis using Loggly

Note :- 
-> Capture images attached under the labs folder for eveidence purpose.   
-> Images are in the name of "brute-force_1 & brute-force_2".
