				                                -:  Linux Suspicious Command Activity Detection using Wazuh SIEM :-

Project Overview - 
-> This project demonstrates how to monitor and detect suspicious command execution activities on a Linux endpoint using Wazuh SIEM.
-> Custom detection rules were created to identify potentially malicious commands commonly used by attackers, including -
* Bash shell execution
* File download attempts using wget
* File download attempts using curl
* Reverse shell-related activities using nc (Netcat)
-> The project simulates attacker behaviour on a Linux machine and showcases how Wazuh can detect and generate alerts in real time through custom detection rules. 

Objective - 
The main objectives of this project are -
* Enable command logging on Linux
* Monitor command execution activities
* Create and deploy custom Wazuh detection rules
* Detect suspicious Linux commands in real time
* Perform threat hunting using Wazuh SIEM
* Understand SOC monitoring and investigation workflows

Lab Setup
Component		      Purpose
Physical Laptop		Wazuh Cloud Dashboard
Kali Linux VM		Monitored Linux Endpoint
Wazuh Agent		    Log Collection and Monitoring
VMware Workstation	Virtualization Platform

Technologies Used - 
* Wazuh SIEM
* Kali Linux
* Wazuh Agent
* Linux Bash
* XML Rule Development
* Threat Hunting

Enable Command Logging in Bash -
Step 1 -> Open .bashrc file(nano ~/.bashrc) -> Add the following lines at the bottom of the file
          # Enable Custom Command Logging 
	    export PROMPT_COMMAND='history 1 >> /tmp/cmd.log'
Step 2 -> Save and exit the file. (To save - Ctrl+o and To exit the file - Ctrl+x)
Step 3 -> Reload the bash configuration using cmd (source ~/.bashrc)
Step 4 -> To verify command logging run below cmds and validate the path /tmp/cmd.log
	  Cmds to run (bash test | wget https://examplefile.com/general/exe/1-mb-exe-file | curl https://example.com)
	  To validate the ouput run cmd (cat /tmp/cmd.log)

Configure Wazuh Agent to Monitor Command Logs -
Step 1 -> Open Wazuh configuration file cmd (sudo nano /var/ossec/etc/ossec.conf)
Step 2 -> Add the below configuration before </ossec_config> and save the file 
	  <localfile> 
            <log_format>syslog</log_format> 
            <location>/tmp/cmd.log</location> 
	  </localfile>
Step 3 -> Restart the Wazuh agent (sudo systemctl restart wazuh-agent)

Create Custom Wazuh Detection Rules -
Step 1 -> Open Wazuh Rule Editor in Wazuh Dashboard.-> Create a new custom rule file (Log_Injection_Suspicious_Activity_Detection.xml)
Step 2 -> Add the below rules and save the file and click on "Reload"
	  <group name="linux_suspicious_activity"> 
	    <rule id="110500" level="12"> 
	      <match>bash</match> 
	      <description>Suspicious Bash Shell Activity Detected</description> 
	      <group>shell,linux,command_execution,</group> 
	    </rule> 
	    <rule id="110501" level="12"> 
	      <match>wget</match> 
	      <description>Suspicious File Download Activity Detected</description> 
	      <group>download,linux,</group> 
	    </rule> 
	    <rule id="110503" level="12"> 
	      <match>curl</match> 
	      <description>Suspicious Curl Download Activity Detected</description> 
	      <group>download,linux,</group> 
	    </rule> 
	    <rule id="110502" level="15"> 
	      <match>nc</match> 
	      <description>Possible Reverse Shell Activity Detected</description> 
	      <group>reverse_shell,linux,</group> 
	    </rule> 
	  </group>

Simulate Attacker Activity -
Step 1 -> Run cmds (bash test, which bash) for bash activity
Step 2 -> Run cmds to perfom download activity (wget https://examplefile.com/general/exe/1-mb-exe-file, curl https://example.com)

Verify Alerts in Wazuh Dashboard -
Step 1 -> Navigate -> Threat Hunting → Events
Step 2 -> Click on "Add filter" -> Select agent id, Operator & value click on save
Step 3 -> Search with this query (rule.description:*Suspicious*)

Learning Outcome -
Through this project, I learned - 
* Linux command monitoring techniques
* Wazuh custom rule development
* Log collection and analysis
* Threat hunting in Wazuh SIEM
* Detection engineering concepts
* SOC investigation workflow
