Setps to setup installed and configured Splunk Universal Forwarder on the Windows VM.

* Navigate to splunk offical website download the splunk universal forwarder in endpoint or vitcim laptop. 
* Dubail clikc on downloaded to install selecct (Check this box to accept the License Agreement  & A Splunk Cloud instance) clikc on next
* Next screen create a local admin account id and password and or host name and port leave blank because it required in entriprize level click on finsh.

Steps to Connect the universal forwarder to splunk cloud

* On your physical laptop, open Splunk Cloud and navigate to Universal Forwarder in left menu
* Click on "Download Universal Forwarder Credentials"  and save the ".spl" file in particular location.
* Open power shell as admin in endpoint or vitcim laptop and run the below cmds
  -> cd "C:\Program Files\SplunkUniversalForwarder\bin"
  -> .\splunk.exe install app "C:\Users\Narayana\Desktop\splunkclouduf.spl"
  -> Run the cmd .\splunk.exe restart
* Verfiy the splunk dashboard for events and logs.
* Create the "inputs.conf" file to store configuraction amd instructions for send all system genrated logs to splunk. Paste the below details and restart the splunk     demon and verfiy the dashboard for windows logs 
  
  [WinEventLog:Security]
  disabled = 0
  index = main
  renderXml = true

  [WinEventLog:System]
  disabled = 0
  index = main
  renderXml = true

  [WinEventLog:Application]
  disabled = 0
  index = main
  renderXml = true

