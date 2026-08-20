Port Scan Detection and Investigation using Splunk Cloud

Attack Perfom Steps -

* Collect the Ip of the target system using cmd ipconfig.
* Run Nmap from Kali using ip cmd to gather open ports info - sudo nmap -sS 192.168.200.128 -p 1-100
* Check the for event in splunk using query "index=* 5157"

