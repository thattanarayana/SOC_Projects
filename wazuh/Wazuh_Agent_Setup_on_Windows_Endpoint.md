							                                    -: Wazuh Agent Setup on Windows Endpoint :-

This guide explains how to install and configure the Wazuh Agent on a Windows Virtual Machine (endpoint device) and connect it to a locally hosted/on-premises Wazuh Server running on the host machine.

The setup helps you monitor Windows security events, detect suspicious activities, and analyze logs directly from your Wazuh Dashboard in a SOC lab environment.

Architecture:-
Windows VM (Agent) -> Wazuh Agent -> Host Machine (Wazuh Server + Dashboard) -> Wazuh Dashboard Alerts & Monitoring

Step 1 — Get Wazuh Server IP Address
         Get Wazuh Server IP Address On Windows Host -> Open Command Prompt run cmd "ipconfig" check for Wireless LAN adapter 
         Wi-Fi: (IPv4 Address)
Step 2 — Verify VM Connectivity
	       Check VM Can Reach Host -> Open Command Prompt inside VM run cmd (ping 192.168.168.1"enter ip which you foun")
         Check for output it display ping statistics in bytes 
Step 3 — Configure VMware NAT Network
	       Configure VMware NAT to avoid dynamic ip change issues -> Open VMware Workstation on Top menu clikc on Edit → Virtual Network Editor
Step 4 — Configure VMnet8 -> Select "VMnet8"

	 | Setting                        | Value         |
     | ------------------------------ | ------------- |
 	 | Network Type                   | NAT           |
	 | DHCP                           | Enabled       |
	 | Connect a host virtual adapter | Enabled       |
	 | Use local DHCP service         | Enabled       |
	 | Subnet                         | 192.168.168.0 |
Step 5 — Configure Windows VM Network Adapter
	       Configure Windows VM to Use NAT ->Shut Down Windows VM -> Open VMware Settings click on "Edit Virtual machine settings" 
Step 6 — Enable NAT Adapter
	       Clikc on "Network Adapter" -> select "NAT: Used to share the host's IP addess -> click on "Ok"
Step 7 — Deploy New Wazuh Agent
	       * Now click "Deploy new agent" -> fill deatil based on you requirment -> Select "WINDOWS" -> MSI 32/64 bits
         * Enter Server Address -> "Server address:" -> "192.168.168.1" clikc on rember server address if needed
         * Enter Agent Name -> Assign an agent name -> "windows-vm" (The agent name must be unique. It can’t be changed once   
	         the agent has been enrolled.) Next -> Leave Group as Default "Default"
	       * Wazuh Generates Commands after entering details "You will see commands appear automatically under" and Start the agent
	       * Inside Windows VM Open -> run as administrator "PowerShell" -> Paste copied command -> Press ENTER -> Wait for installation to complete. 
	       * cmd to download agent (Invoke-WebRequest -Uri https://packages.wazuh.com/4.x/windows/wazuh-agent-4.14.0-1.msi-OutFile $env:tmp\wazuh-agent;     msiexec.exe /i$env:tmp\wazuh-agent /q WAZUH_MANAGER='192.168.168.1'WAZUH_AGENT_NAME='windows-vm') 
	       * Wai to finsh the installation
         * START AGENT after the instlallation using cmd (NET START WazuhSvc)
	       * Check wazuh dashboard -> Agent Summary -> check Agents (1)
		 




