
Incident Summary (rule.description) -

During a controlled SOC lab exercise, Wazuh generated Alert ID 92031 after detecting execution of the Windows account discovery command net user. 
Sysmon Event ID 1 recorded the creation of net1.exe, launched by net.exe under the NT AUTHORITY\SYSTEM account. 
The activity corresponds to MITRE ATT&CK technique T1087 (Account Discovery). 
Investigation found no associated account creation, privilege escalation, persistence, or lateral movement activity. 
Based on available evidence, the alert is classified as a True Positive detection of account enumeration behavior but assessed as benign laboratory activity with no malicious impact.

Investigation Note (rule.groups:sysmon) -

Wazuh Rule 92205 generated a high-severity alert indicating PowerShell created a file within a Windows system directory. 
Investigation revealed the file __PSScriptPolicyTest_*.ps1 is a legitimate temporary PowerShell execution policy validation file created by powershell.exe running under NT AUTHORITY\SYSTEM. 
No evidence of encoded commands, malicious payloads, unauthorized access, or persistence mechanisms was observed. 
The activity is consistent with normal Windows PowerShell behavior and is classified as a False Positive.
