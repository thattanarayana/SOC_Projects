Investigation Findings - 
After detecting multiple Wazuh alerts (Rule ID 110500, 110501, and 110503), the related Linux command execution logs were analyzed. 
The alerts originated from the monitored endpoint kali-vm (192.168.200.129) and were generated from command activity recorded in /tmp/cmd.log.

Event analysis confirmed the execution of the command = which bash
which triggered the alert "Suspicious Bash Shell Activity Detected" (Rule ID 110500). 
The command was successfully captured by Wazuh and matched the custom detection rule configured to identify shell-related activity.

Further investigation identified a file download event through the command = wget https://examplefile.com/general/exe/1-mb-exe-file
which generated the alert "Suspicious File Download Activity Detected" (Rule ID 110501). 
Review of the endpoint confirmed that the file was successfully downloaded to the user's home directory. 
The downloaded file was subsequently analyzed using VirusTotal, where no security vendors identified the file as malicious at the time of investigation.

Additional analysis identified the execution of = curl https://example.com
which triggered the alert "Suspicious Curl Download Activity Detected" (Rule ID 110503). 
The command successfully established an HTTP connection and retrieved content from the specified URL, confirming that the detection rule functioned as intended.

Investigation efforts were performed to identify the user responsible for executing the commands, determine the parent process, and review process creation activity. 
However, the current logging configuration only records command history entries from /tmp/cmd.log and does not provide user attribution, process identifiers (PID), parent process information (PPID), or session details. As a result, the exact execution context could not be determined.

Additional checks were conducted for evidence of persistence mechanisms, privilege escalation attempts, reconnaissance activity, suspicious outbound network connections, lateral movement, and execution of the downloaded file. 
No related events or indicators of compromise were identified during the investigation.

Based on the collected evidence, the activity was classified as a True Positive resulting from authorized SOC laboratory testing. While the alerts accurately detected command execution and file download behavior, there was no evidence of malicious execution, persistence, privilege escalation, or post-compromise activity. The downloaded file remained unexecuted, and the overall impact to the system was determined to be minimal.
