Investigation Findings :-

Incident Classification:
Incident Type - Privilege Escalation / Unauthorized Administrative Group Modification
Severity - High
Status - True Positive
Affected Asset - windows-vm
Affected User(s) -
narayana (Initiating User)
ramesh (Newly Created Administrative Account)
kiran (Created and Later Removed Account)

Root cause -
User "narayana" successfully authenticated to the Windows system through SSH service (OpenSSH) and performed account management activities.
During the investigation, it was identified that the user created new local accounts and added them to the local Administrators group, resulting in privilege escalation events detected by Wazuh.
The following activities were observed:
Creation of user account ramesh
Creation of user account kiran
Addition of both accounts to the Builtin\Administrators group
Administrative group membership modifications
Subsequent removal/deletion of the kiran account
ramesh account remained active with Administrator privileges

Investigation Summary -
Account Creation - Windows Security logs confirmed that ramesh and kiran user accounts were successfully created.
Privilege Escalation - Event ID 4732 confirmed that both accounts were added to the local Administrators group.
	               Wazuh generated Privilege Escalation alerts (Rule ID: 100201) for this activity.
Successful Login - Event ID 4624 showed a successful SSH login through (C:\Windows\System32\OpenSSH\sshd.exe)
Authenticated user - narayana No failed login attempts were observed.

Persistence Check - 
ramesh account is still active. 
ramesh remains a member of the Administrators group.
kiran account was removed.
Additional Investigation

No evidence of - 
Malware activity
Suspicious process execution
Credential theft
Lateral movement
Additional compromised accounts was found during the investigation.

Impact -
New local user accounts were created.
Administrator privileges were assigned.
Local Administrators group membership was modified.
One privileged account (ramesh) remained active.

Conclusion - TRUE POSITIVE
Wazuh successfully detected a privilege escalation activity where user narayana created new accounts and added them to the Administrators group.
One account (kiran) was later removed, while ramesh remained active with Administrator privileges.
No signs of malware, credential theft, lateral movement, or further compromise were found. The activity was successfully detected and investigated in the SOC lab environment.
