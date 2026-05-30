					                               -: Windows Privilege Escalation Detection using Wazuh SIEM :- 

Project Objective -
-> This project demonstrates how to simulate and detect Windows Privilege Escalation activities using Wazuh Cloud SIEM.
-> The lab focuses on monitoring suspicious administrative actions such as -
* User account creation
* Adding users to the Administrators group
* Privilege escalation detection
* Command-line activity monitoring
-> Detection is achieved using  Windows Security Logs, Sysmon Logs, Custom Wazuh Rules

Lab Environment - 
Component			Purpose
Windows Virtual Machine		Target endpoint
Wazuh Cloud SIEM		Log monitoring & alerting
Sysmon				Advanced Windows event logging
Wazuh Agent			Endpoint log forwarding

Verify wazuh agent & sysmon service status - 
Step 1 - On Windows VM open power shell and run cmd (services.msc) to view running services
	 check (Wazuh Agent and Sysmon Service ) should be running

Enable Required Windows Auditing Policies -
Step 1 - Open "Local Security Policy" -> Go to "Security Settings" -> Double-click on "Advanced Audit Policy Configuration"
Step 2 - Expand "System Audit Policies - Local Group Policy Object" -> Enable Process Creation Logging -> Click on "Detailed Tracking"
Step 3 - Double-click on "Audit Process Creation" -> Enable Configure the following audit events, Success & Success -> clikc on "Apply" and click on ok
Step 4 - Double-click on "Privilege Use" -> Enable (Audit Sensitive Privilege Use, Audit Non Sensitive Privilege Use)
Step 5 - Double-click on "Account Management" -> Enable (Audit User Account Management, Audit Security Group Management)
Step 6 - Double-click on "Logon/Logoff" -> Enable (Audit Logon, Audit Special Logon)
Step 7 - To apply policy open cmd as administrator -> run cmd (gpupdate /force) wait untill it finsh
Step 8 - Verify auditing enabled or not using cmd (auditpol /get /category:*)

Enable Command Line Logging -
Open PowerShell as Administrator -> Run the below cmd to enable cmd line loggin -> 

Simulate Privilege Escalation Attack -
Step 1 - To create user run the cmd -> net user socuser Pass@123 /add
Step 2 - To assgin the admin Privilege -> net localgroup administrators socuser /add
Step 3 - To delete user -> net user attacker /delete
Step 4 - Check events in wazuh dashboard

Custom Wazuh Rule Detection - 
You can create custom Wazuh rules to detect -
* Unauthorized administrator access
* Suspicious account creation
* Privilege escalation attempts
* Sensitive privilege usage

Learning Outcomes -
After completing this project, you will understand -
* Windows Privilege Escalation Detection
* Windows Security Auditing
* Sysmon Event Monitoring
* Wazuh SIEM Alert Investigation
* Command-Line Activity Logging
* Custom Wazuh Rule Creation
* SOC Investigation Workflow

