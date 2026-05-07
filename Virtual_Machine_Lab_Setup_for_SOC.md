							                            -: Setup of Virtual Machine Lab for SOC :-
 
This guide helps beginners set up a SOC (Security Operations Center) Lab using :-
* Oracle VirtualBox
* Kali Linux
* Windows 10

Table of Contents :-
1. Install VirtualBox
2. Setup Kali Linux in VirtualBox
3. Setup Windows 10 in VirtualBox
4. Install VirtualBox Guest Additions
5. Benefits of Guest Additions


                                                              1. Install Oracle VirtualBox :- 

Step 1: Download VirtualBox
-> Go to the official website - https://www.virtualbox.org/ 
-> Oracle VirtualBox
-> Click on Download and download the version for your operating system.

Step 2: Install VirtualBox 
-> After the download completes
-> Double-click the installer file
-> Follow the installation wizard
-> Keep default settings unless you want to customize them
-> Click Install
-> After installation, open VirtualBox.


                                                             2. Kali Linux Setup in VirtualBox :- 

Step 1: Download Kali Linux ISO
-> Go to - https://www.kali.org/get-kali/#kali-platforms
-> Kali Linux Downloads
-> Download "Open Installer Images"
-> Select 64-bit Version
-> Download "kali-linux-2026.x-installer-amd64.iso"

Step 2: Create Kali Linux Virtual Machine  
-> Open VirtualBox and click "New"
Fill VM Details
Option		   Value
Name	        Kali Linux
Folder	        Leave Default
ISO Image	Select downloaded Kali ISO
Type	        Linux
Version	        Debian (64-bit)
-> Click "Next".

Step 3: Allocate Hardware Resources 
-> Recommended 
Resource	   Value
RAM		4 GB or More
CPU		2 Cores
Storage		50 GB
-> Click "Specify Virtual Hardware"
-> Then click Finish.

Step 4: Start Kali Linux Installation 
-> Select the Kali VM
-> Click Start
-> VirtualBox will boot using the Kali ISO file.

Kali Linux Installation Steps :-
-> Select Basic Settings
-> Choose (Country, Language, Keyboard Layout)
-> Create User Account
-> Enter (Username & Password)

Disk Partitioning (Manual Method) :-
Step 1: Select Partitioning Type
-> Choose "Manual"

Step 2: Select Virtual Disk
-> Select "VBOX HARDDISK 50 GB FREE SPACE"
-> Choose "Create new empty partition table"
-> Select "Yes"

Step 3: Create Root Partition
-> Select "FREE SPACE"
-> Then choose "Create a new partition"
-> Configuration values
Setting		Value
Size		50 GB
Type		Primary
Mount Point	/
Use As		Ext4 Journaling File System
-> Select "Done setting up the partition"

Step 4: Create Swap Partition
-> Again select "FREE SPACE"
-> Configuration values 
Setting	        Value
Size	      4.4 GB
Type	      Logical
Use As	      Swap Area

Step 5: Save Partition Changes
-> Choose "Write changes to disk"
-> Select "Yes"

Step 6: Select Desktop Environment
-> Choose the desktop environment you want.
-> Recommended for beginners (XFCE (Lightweight), GNOME (Modern UI))
-> Wait for installation to complete.


                                               3. Windows 10 Setup in VirtualBox


Step 1: Download Windows 10 ISO
-> Go to - https://www.microsoft.com/en-us/software-download/windows10?msockid=250979f2e7b0674102d36f1de6d26603 "Windows 10 Download Page"
-> Under "Create Windows 10 installation media"
-> Click "Download Now"
-> This downloads the Media Creation Tool.

Step 2: Create Windows ISO
-> Open the Media Creation Tool.
-> Choose "Create installation media (USB flash drive, DVD, or ISO file) for another PC"
-> Click "Next".

Step 3: Select Windows Options
-> Choose (Language, Edition, Architecture (64-bit))
-> Click "Next".

Step 4: Select ISO File
-> Choose "ISO file"
-> Click "Next" and select download location.
-> Wait for the ISO download to complete.

Create Windows Virtual Machine :-
-> Open VirtualBox and click "New"
-> Fill VM Details
Option	        Value
Name	        Windows 10
Folder	        Leave Default
ISO Image	Select downloaded Windows ISO
Type	        Microsoft Windows
Version	        Windows 10 (64-bit)
-> Click "Next".

-> Allocate Hardware Recommended Resources
Resource	Value
RAM	        4 GB or More
CPU	        2 Cores
Storage	        60 GB
-> Click "Specify Virtual Hardware" "Specify Virtual Hard Disk"
-> Then click "Finish"

Start Windows Installation :-
-> Select the Windows VM
-> Click "Start" VirtualBox will boot using the Windows ISO.

Windows Installation Steps :-

Step 1: Basic Setup
-> Select (Language, Time Format, Keyboard Layout)
-> Click "Next"

Step 2: Install Windows
-> Click "Install Now"

Step 3: Product Key
-> Choose "I don't have a product key"

Step 4: Select Windows Version
-> Recommended "Windows 10 Pro" Click "Next".

Step 5: Accept License
-> Check "I accept the license terms" Click "Next".

Step 6: Choose Installation Type
-> Select Custom: Install Windows only (advanced)

Step 7: Select Virtual Disk
-> Choose "Drive 0 Unallocated Space"
-> Click "Next" Windows installation will begin.
-> Wait for Installation
-> Windows will (Copy files, Install features, Install updates, Restart automatically) Wait until setup completes.
-> Complete Initial Windows Setup Follow on-screen steps (Username, Password, Privacy settings, Region)

                             
                                             4. Install VirtualBox Guest Additions


Guest Additions improve VM performance and usability.

Step 1: Insert Guest Additions ISO
-> Inside VirtualBox menu:
-> Devices → Optical Drives → VBoxGuestAdditions.iso

Step 2: Open Guest Additions
-> Inside Windows VM "This PC → CD Drive (D:)"
-> Double-click "VBoxWindowsAdditions.exe"

Step 3: Restart VM
-> After installation completes "Restart the system"

                  
                                            5. Benefits of Guest Additions


After installing Guest Additions, you get:
* Full Screen Support
* Better Graphics
* Smooth Mouse Movement
* Shared Clipboard (Copy-Paste)
* Better Performance
* Drag and Drop Support

Recommended SOC Lab Setup
VM	          Purpose
Kali Linux	Attacking / Security Testing
Windows 10	Victim Machine
VirtualBox	Virtualization Platform


Resources Used :-

VirtualBox Documentation - https://www.virtualbox.org/wiki/Documentation?utm_source
Kali Linux Official Docs - https://www.kali.org/docs/?utm_source
Microsoft Windows Documentation - https://learn.microsoft.com/en-us/windows/?utm_source
