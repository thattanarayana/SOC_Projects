							     -: Setup of VMware / Virtual Machine Lab for SOC :-

Overview :-
This guide helps you build a beginner-friendly SOC (Security Operations Center) lab using -
* VMware Workstation Pro
* Windows 10 Virtual Machine
* Kali Linux Virtual Machine

Table of Contents :-
* Installation of VMware Workstation Pro
* Setup Kali Linux in VMware 
* Setup Windows 10 in VMware 
* Install VMware Guest Additions
* Benefits of Guest Additions

Architecture -
Host Windows Laptop
└── VMware Workstation Pro
      ├── Windows 10 VM
      └── Kali Linux VM

							         1. Install VMware Workstation Pro

Setp 1 — Go to - https://www.vmware.com/ -> Select "Broadcom Support" 
Setp 2 — In Broadcom website - https://support.broadcom.com/ -> click on "Register" and clikc on login
Setp 3 — Go to "My Downloads" -> Click on "Free Software Downloads available HERE" -> Search for "VMware Workstation Pro"
Setp 4 — Click on "VMware Workstation Pro" -> Select Version, Type of windows, Which type of  VMware Workstation Pro
Setp 5 — Double clikc on file and install

							2. Windows 10 Setup in VMware Workstation Pro
							
Setps to download windows ISO image file :-
Step 1 — Download Windows 10 ISO -> Go to - https://www.microsoft.com/en-us/software-download/windows10?msockid=250979f2e7b0674102d36f1de6d26603 "Windows 10            Download Page" -> Under "Create Windows 10 installation media" -> Click "Download Now" -> This downloads the Media Creation Tool.
Step 2 — Create Windows ISO -> Open the Media Creation Tool. -> Choose "Create installation media (USB flash drive, DVD, or 
         ISO file) for another PC" -> Click "Next".
Step 3 — Select Windows Options -> Choose (Language, Edition, Architecture (64-bit)) -> Click "Next".
Step 4 — Select ISO File -> Choose "ISO file" -> Click "Next" and select download location. -> Wait for the ISO download 
         to complete.

Setps to create windows VM :-
Step 1 — Open VMware Click "Create a New Virtual Machine"
Step 2 — Select Configuration choose "Typical (recommended)" and Click "Next"
Step 3 — Select Windows ISO choose "Installer disc image file (iso)" -> Browse and select "Windows 10 ISO" click "Next"
Step 4 — To start Windows Installation click on "Power on this virtual machine"

Windows Installation Steps :-
Step 1 — Basic Setup -> Select (Language, Time Format, Keyboard Layout) -> Click "Next"
Step 2 — Install Windows -> Click "Install Now"
Step 3 — Product Key -> Choose "I don't have a product key"
Step 4 — Select Windows Version -> Recommended "Windows 10 Pro" Click "Next".
Step 5 — Accept License -> Check "I accept the license terms" Click "Next".
Step 6 — Choose Installation Type -> Select Custom: Install Windows only (advanced)
Step 7 — Select Virtual Disk -> Choose "Drive 0 Unallocated Space" -> Click "Next" Windows installation will begin. 
        -> Wait for Installation -> Windows will (Copy files, Install features, Install updates, Restart automatically) Wait until setup completes.         -> Complete Initial Windows Setup Follow on-screen steps (Username, Password, Privacy settings, Region)
Note :- Use local/offline account is recommened.

Install VMware Tools in windows :-
Step 1 — From VMware menu -> VM → Install VMware Tools
Step 2 — Inside Windows VM -> Open DVD drive -> Run installer
Step 3 — Choose "Typical" & Restart VM after installation.
Step 4 — VMware menu -> View → Autosize → Fit Guest Now and View → Full Screen. Shortcut "Ctrl + Alt + Enter"

							                 3. Kali Linux Setup in VMware :- 

Setps to download linux ISO image file :-
Step 1 — Download Kali Linux ISO -> Go to - https://www.kali.org/get-kali/#kali-platforms -> Kali Linux Downloads -> 
         Download  "Open Installer Images" -> Select 64-bit Version -> Download "kali-linux-2026.x-installer-amd64.iso"
Step 2 — Create Kali Linux Virtual Machine
         -> Open VirtualBox and click "New" Fill VM Details Option Value Name Kali Linux Folder Leave Default ISO Image Select downloaded Kali ISO                      Type Linux Version Debian (64-bit) -> Click "Next".
Step 3 — Allocate Hardware Resources -> Recommended Resource Value RAM 4 GB or More CPU 2 Cores Storage 50 GB -> 
         Click "Specify Virtual Hardware" -> Then click Finish.
Step 4 — Start Kali Linux Installation -> Select the Kali VM -> Click Start -> VirtualBox will boot using the Kali ISO file.

Setps to create linux VM :-
Step 1 — Open VMware Click "Create a New Virtual Machine"
Step 2 — Select Configuration choose "Typical (recommended)" and Click "Next"
Step 3 — Select linux ISO choose "Installer disc image file (iso)" -> Browse and select "linux   
       	 (kali-linux-2026.1-installer-amd64) ISO" click "Next"
Step 4 — Linux Type Choose "Linux" & Version "Debian 12.x 64-bit"
Step 5 — VM Name "Kali-Linux" 
Step 6 — Disk Size recommended "50 GB" & Choose "Store virtual disk as a single file"

Kali Linux Installation Steps :-
Step 1 — Start VM clicl "Power on this virtual machine"
Step 2 — Installer Menu choose "Graphical Install"
Step 3 — Select Language and Region (Language, Country, Keyboard layout)
Step 4 — Hostname "kali"
Step 5 — Create Username and Password

Disk Partitioning (Manual Method) :- 
Step 1 — Select Partitioning Type -> Choose "Manual"
Step 2 — Select Virtual Disk -> Select "VBOX HARDDISK 50 GB FREE SPACE" -> Choose "Create new empty partition table" 
         -> Select "Yes"
Step 3 — Create Root Partition -> Select "FREE SPACE" -> Then choose "Create a new partition" -> Configuration values 
         Setting Value Size 50 GB Type Primary Mount Point / Use As Ext4 Journaling File System 
         -> Select "Done setting up the partition"
Step 4 — Create Swap Partition -> Again select "FREE SPACE" -> Configuration values Setting Value Size 4.4 GB Type Logical 
         As Swap Area
Step 5 — Save Partition Changes -> Choose "Write changes to disk" -> Select "Yes"
Step 6 — Select Desktop Environment -> Choose the desktop environment you want. -> Recommended for beginners (XFCE   
         (Lightweight), GNOME (Modern UI)) -> Wait for installation to complete.


Install VMware Tools in Kali :-
Step 1 - Start VM clicl "Power on this virtual machine"
Step 2 - Open terminal and run the below cmds
         sudo apt update
	     sudo apt install -y open-vm-tools open-vm-tools-desktop
	     sudo reboot
         
                                            5. Benefits of Guest Additions

After installing Guest Additions, you get:
* Full Screen Support
* Better Graphics
* Smooth Mouse Movement
* Shared Clipboard (Copy-Paste)
* Better Performance
* Drag and Drop Support

Recommended SOC Lab Setup
VMware	          			    Purpose
Kali Linux	  				Attacking / Security Testing
Windows 10	  				Victim Machine
VMware Workstation Pro	  	Virtualization Platform

Resources Used :-
VMware Documentation            - https://techdocs.broadcom.com/
Kali Linux Official Docs        - https://www.kali.org/docs/?utm_source
Microsoft Windows Documentation - https://learn.microsoft.com/en-us/windows/?utm_source
