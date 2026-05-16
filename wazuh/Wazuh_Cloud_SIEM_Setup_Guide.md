						                                          -: Wazuh Cloud SIEM Setup Guide :- 


A step-by-step guide to set up the cloud version of Wazuh and connect endpoint devices using the Wazuh Agent.

Project Overview :-
* Create a Wazuh Cloud account
* Launch a free Wazuh Cloud environment
* Access the Wazuh Dashboard
* Generate agent installation commands
* Install Wazuh Agent on endpoint systems
* Monitor endpoint activity from the cloud dashboard

Wazuh Cloud Account Creation:-
Step 1 — Open Wazuh Cloud Sign-Up Page
	       Go to website -> https://console.cloud.wazuh.com/sign-up and create trail accoutn using businessmail id
Step 2 — Create Trial Account
	       Fill in all required details: (First name, Last name, Business Email, Phone number, Company, Country, Password) -> Then click "Create Account"
Step 3 — After registration Verify Email Address
	       Open your email inbox
	       Find the verification email from Wazuh
	       Click the verification link
	 
Login to Wazuh Cloud :-
Step 1 — Login to Wazuh Console
	       Go to website -> https://console.cloud.wazuh.com/login and login with verfied mail and password

Create Wazuh Cloud Environment :-
Step 1 — Start Free Trial Environment
	       Click on "Start trial" (yellow button) -> Fill all required deatils for "Create your environment" -> Click on "Start your free trial" (yellow button)
Step 2 — Wait for Environment Creation
	       Wait for some time until it cretae environment or it siplay "Environment details" page Access the Wazuh Dashboard

Access the Wazuh Dashboard:-
Step 1 — Open Wazuh Dashboard
	       Open Wazuh Dashboard Click the yellow button "Open Wazuh" it will navigate to wazuh bashboard page
	 
Get Default Login Credentials:-
Step 1 — Generate Dashboard Credentials
	       To get id and password select "Default credentials" from "Manage" dropdown wait until system genrate id and password.		
	       Use default credentials to login dashboard
Step 2 — Login to Dashboard

Deploy Wazuh Agent on Endpoint Device:-
Step 1 — Open Agent Deployment 
	       Click on "Deploy new agent" to setup agent in endpoint 
Step 2 - Fill the to genrate cmd to download and intall agent 
	     Select the package to download and install on your system:
         Server address:
         Server address: (This is the address the agent uses to communicate with the server. Enter an IP address or a fully qualified domain name (FQDN))
         Assign an agent name:
Step 3 - Copy and run the following commands to download and install the agent: (cmd will display at page) wai untill finsh installation 
Step 4 - Once finsh the download and installation porcess Start the agent using cmd "NET START Wazuh"	
Step 8 - Go to wazuh dashboard -> check for agent status it should be active  	 


	 
By completing this project I have gain knowledge about :-
* Cloud SIEM deployment
* Endpoint agent management
* Security event monitoring
* Centralized log collection
* SOC environment basics








