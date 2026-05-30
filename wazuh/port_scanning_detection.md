							                                      -: Port Scanning Detection in SOC Lab using Wazuh :-

Project Overview -

-> This project demonstrates how to simulate a Port Scanning attack using Nmap from a Kali Linux attacker machine and detect the reconnaissance activity inside the Wazuh Cloud SIEM Dashboard using -
* Windows Firewall Logs
* Sysmon Logs
* Custom Detection Rules
* MITRE ATT&CK Mapping
-> The lab helps understand how attackers perform network reconnaissance and how SOC analysts can identify suspicious scanning behavior in real-time.

Technologies Used - 
* Kali Linux
* Nmap
* Windows VM
* Sysmon
* Wazuh SIEM
* Windows Firewall Logs

Lab Setup -> 
Device			Role
Physical Laptop		Wazuh Cloud Dashboard
Kali Linux VM		Attacker Machine
Windows VM		Victim Endpoint
Wazuh Agent		Installed on Windows VM

Objective -
The objective of this lab is to -
* Simulate a port scanning attack using Nmap
* Generate network reconnaissance activity
* Collect Sysmon and Firewall logs in Wazuh
* Detect scanning behavior inside the Wazuh dashboard
* Understand reconnaissance techniques used by attackers

Step 1 -> Nmap installation in Kali Linux - 
	 -> Open terminal in Kali -> Run cmd "sudo apt update " to update OS 
	 -> run cmd to donload and install nmap "sudo apt install nmap -y"
	 -> Run cmd to verify namp installation "nmap --version"
Step 2 -> Enable Windows Firewall Logging - 
	 -> Open windows defender "Windows Defender Firewall with Advanced Security" 
	 -> Go to Properties → Private Profile → Logging → Customize
	 -> Enable Log dropped packets = Yes, Log successful connections = Yes
Step 3 -> Configure Wazuh Agent to Collect Logs -
         -> Open Windows VM -> Edit -> C:\Program Files (x86)\ossec-agent\ossec.conf
	 -> Add below values inside <ossec_config> -> Save and exit 
	   <localfile>
  	     <location>Microsoft-Windows-Sysmon/Operational</location>
	     <log_format>eventchannel</log_format>
	   </localfile>

	  <localfile>
	    <location>C:\Windows\System32\LogFiles\Firewall\pfirewall.log</location>
  	    <log_format>syslog</log_format>
	  </localfile>
	 -> Restart Wazuh Agent -> run the cmd "Restart-Service Wazuh" in powershell as Administrator

Simulate Port Scanning Attack -
Step 1 -> Open terminul in kali linux 
       -> Rune the cmd to perform (sudo nmap -Pn -p- 192.168.200.128 / sudo nmap -sS -Pn 192.168.200.128)attack 
Step 2 -> Check events in wazuh dashboard    
Step 3 -> Run the below any query to find the scanning activity
	  -> Discovery Activity run (rule.description:"Discovery activity executed")
	  -> Sysmon Network Events (rule.groups:sysmon)
	  -> Discovery MITRE Technique (rule.mitre.id:T1087)

Expected Detection Behavior After the scan -
* Windows Firewall logs multiple connection attempts
* Sysmon records network activity
* Wazuh collects and analyzes logs
* Alerts are generated for reconnaissance behavior
* SOC analysts can investigate suspicious scanning attempts

Learning Outcomes - 
By completing this lab, I have understand -
* How attackers perform port scanning
* How Nmap reconnaissance works
* How to detect scanning activity in Wazuh
* How Sysmon and Firewall logs help in threat detection
* Why reconnaissance activity is important in SOC monitoring
* How to identify suspicious network behavior

