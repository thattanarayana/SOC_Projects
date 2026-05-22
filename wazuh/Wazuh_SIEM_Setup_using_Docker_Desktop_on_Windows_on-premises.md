					           -: Wazuh SIEM Setup using Docker Desktop on Windows on-premises:-


A complete guide to install and configure the open-source SIEM tool Wazuh using Docker Desktop on Windows on-premises.

Overview :-
Install Docker Desktop on Windows
Download and configure Wazuh Docker package
Start Wazuh Manager, Dashboard, and Indexer
Access the Wazuh Dashboard from browser

Prerequisites :-
Windows 10/11 (64-bit)
Virtualization Enabled in BIOS
Hyper-V Enabled
Windows Subsystem for Linux (WSL2)
Minimum 8 GB RAM Recommended

Docker Desktop Installation Steps :-
Step 1 — Download Docker Desktop
         Go t- website - https://www.docker.com/products/docker-desktop/? Click on "Download Docker Desktop" 
	       Make sure to download the correct version for your system: Windows – AMD64
Step 2 — Run the Installer
 	       Duble click on downloaded file "Docker Desktop Installer.exe"
	       If Windows asks Do you want to allow this app to make changes? -> Click "Yes" and choose "Use recommended settings" wait complete installation process.
Step 3 — Installation Configuration
	       Docker Installation Screen -> You will see checkboxes like "Use WSL 2 instead of Hyper-V" & "Add shortcut to desktop"
         Keep default settings Click "OK" 
Step 4 — Complete Installation
	       Wait for installation to complete -> click on "Close and restart" after the sucessful installation.

Wazuh Dashboard Setup:-
Step 1 — Open Docker Desktop
	       Open Docker Desktop and Docker show (Terms and conditions) -> Click on "Accept"
Step 2 — Skip Sign In
         In next page it ask for Sign Up or Continue without signing in -> click "Continue without signing in" 
Step 3 — Verify Docker Engine
	       Wait for Docker to fully start -> Bottom-left should show "Engine running" it is indication of Docker is working 
         correctly.

Wazuh folder creation steps using powershell :-  
Step 1 - Create Wazuh Folder "mkdir C:\wazuh-docker" and move to created folder "cd C:\wazuh-docker"
Step 2 - Download Wazuh Docker Packag useing cmd 
         (Invoke-WebRequest -Uri "https://packages.wazuh.com/4.14/wazuh-docker-4.14.0.tar.gz" -OutFile "wazuh-docker-4.14.0.tar.gz")
         Wait until download completes.
Step 3 - Extract Package using cmd (tar -xvf wazuh-docker-4.14.0.tar.gz) 
Step 4 - Go Into Single-Node Folder to generate certificates(cd single-node)
Step 5 - Generate Certificates using cmd (docker-compose -f generate-indexer-certs.yml run --rm generator)
Step 6 - Start sazuh stack after certificates genration is finshed (docker-compose up -d)
Step 7 - Start Wazuh using cmd (docker-compose up -d) First startup can take 10–20 minutes. 
Step 8 - Verify Containers using cmd (docker ps) -> You should see (wazuh.manager, wazuh.dashboard, wazuh.indexer)
Step 9 - Open Dashboard -> Open browser -> https://localhost -> login with default username and password 
         Username: admin
         Password: SecretPassword
		 






