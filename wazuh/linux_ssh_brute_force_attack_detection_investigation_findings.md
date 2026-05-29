Investigation Findings :-

After detecting multiple Wazuh alerts (Rule ID 60122), the related Windows Security logs were analyzed. 
The alerts were generated from Windows Event ID 4625, indicating failed authentication attempts against the Windows OpenSSH service (sshd.exe).

The target account was identified as "narayana". 
Event analysis showed that the authentication failures were caused by incorrect passwords (Status: 0xC000006D, SubStatus: 0xC000006A). 
The logon type was identified as Type 8 (NetworkCleartext), which is consistent with SSH authentication activity.

Further investigation was performed to determine whether the attacker successfully gained access to the system. 
Searches for successful logon events (Event ID 4624) returned no results. 
Additional investigation for privileged logons (Event ID 4672), process creation activity (Event ID 4688), account discovery, new user creation (Event ID 4720), and group membership modifications (Event ID 4732) also returned no related events.

Based on the collected evidence, the attack was classified as an unsuccessful SSH brute-force attempt. The attack was detected and logged by Windows Security Auditing and successfully forwarded to Wazuh, allowing timely identification and investigation. No evidence of unauthorized access, privilege escalation, persistence, or post-compromise activity was observed.
