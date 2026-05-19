					      -: Wazuh Agent Installation on Endpoint Windows VM :-

This guide explains how to install and configure the Wazuh Agent inside a windows & Kali Linux virtual machine running on VMware Workstation and connect it to the Wazuh Cloud dashboard.
This process is for wazuh cloud version 

Deploy Wazuh Agent on Endpoint Windows Device:- 
Step 1 — Open Agent Deployment 
	       Click on "Deploy new agent" to setup agent in endpoint 
Step 2 - Fill the form to genrate cmd to download and intall agent 
         Select the package to download and install on your system 
         Server address: (This is the address the agent uses to communicate with the server. Enter an IP address or a fully qualified domain name (FQDN)) 
         Assign an agent name: 
Step 3 - Copy and run the following commands to download and install the agent: (cmd will display at page) wait untill finsh installation 
Step 4 - Once finsh the download and installation porcess Start the agent using cmd "NET START Wazuh" 
Step 5 - Go to wazuh dashboard -> check for agent status it should be active						

				        -: Wazuh Agent Installation on Endpoint Kali Linux VM :-

Deploy Wazuh Agent on Endpoint Linux Device:- 
Step 1 - Run cmd "sudo apt update" This cmd refreshes Kali Linux package information and helps avoid dependency issues.
Step 2 — Open Agent Deployment 
	       Click on "Deploy new agent" to setup agent in endpoint
Step 3 - Fill the form to genrate cmd to download and intall agent 
         Select the package to download and install on your system 
         Server address: (This is the address the agent uses to communicate with the server. Enter an IP address or a fully qualified domain name (FQDN)) 
         Assign an agent name: 
Step 3 - Copy and run the following commands to download and install the agent: (cmd will display at page) wait untill finsh installation 
Step 4 - After installation run the following cmd's 
	       sudo systemctl enable wazuh-agent
	       sudo systemctl start wazuh-agent
	       sudo systemctl status wazuh-agent
Step 5 - Go to wazuh dashboard -> check for agent status it should be active and check agents count is (2)


						

