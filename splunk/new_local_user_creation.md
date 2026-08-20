New Local User Account Creation & Privileged Group Membership Change Detection

New Local User Account Detection Event ID: 4720

Privileged Group Membership Change Detection Event ID: 4732

Existed user deletion Event Id: 4726

* Create and deleted local Windows accounts using the net user command and analysed the corresponding security events.
* Added a test user to the local Administrators group and investigated the generated security event.
 
Attack Simulation/ steps 

-> Get target IP address Open command prompt on the windows machine and run cmd = ipconfig Copy the IPv4 address of the target system
-> Run ssh cmd along with ipv4 address to get remote access to system
-> To create user run the cmd -> net user socuser Pass@123 /add
-> To assgin the admin Privilege -> net local group administrators socuser /add
-> To delete user -> net user attacker /delete
-> Check all events in splunk dashboard using search & reporting option. 

Learning Outcomes - After completing this project, you will understand -

* Windows Privilege Escalation Detection
* Windows Security Auditing
* Command-Line Activity Logging
* Cmd history monitoring & export reports in splunk
