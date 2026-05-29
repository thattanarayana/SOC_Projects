Investigation Findings Of Sucessful Login :-

A simulated SSH brute-force attack was performed from a Kali Linux attacker machine against a Windows endpoint running OpenSSH Server. 
Multiple authentication failures were detected in Wazuh (Rule ID 60122), followed by a successful authentication event (Rule ID 60106).
Further investigation confirmed that the successful login originated from the Kali Linux system and established a remote SSH session on the Windows endpoint. 
Additional analysis was performed for privileged logon activity (Event ID 4672), process creation (Event ID 4688), account discovery, new user creation (Event ID 4720), group membership modifications (Event ID 4732), account lockouts (Event ID 4740), persistence mechanisms, and scheduled task creation. 
No related malicious activity was identified.
The investigation concludes that the attack simulation successfully demonstrated SSH brute-force detection capabilities in Wazuh. 
Although the attacker obtained valid access to the target system, no post-compromise actions, privilege escalation, persistence, or lateral movement activities were observed.
