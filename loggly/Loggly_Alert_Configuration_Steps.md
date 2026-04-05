		                                              -: Loggly Alert Configuration – Steps :-

This explain how the process of creating and configuring alert's in loggly for effective log monitoring and incident detection.

Steps to Create an Alert -

* Create a Filter -
  Apply relevant search filters to identify specific log events (e.g., failed logins, SSH errors).

* Save the Search -
-> Click on the ⭐ (Favorite) icon.
-> Select “Save this search as”.
-> Provide a meaningful name based on the event (e.g., SSH_Failure_Alert).

* Initiate Alert Creation -
-> After saving, click on “Save then create alert”.
-> This will redirect you to the alert configuration page.

* Configure Alert Details
-> Enter a descriptive Alert Name.
-> Under “Saved Search”, ensure your previously saved search is selected.

* Define Alert Conditions -
  Set conditions based on requirements (e.g., trigger alert if event count > 10).

* Set Alert Trigger Options -
-> Choose how alerts should be triggered (email, webhook, etc.).
-> Provide necessary configuration details (email address, endpoints, etc.).

* Set Evaluation Frequency -
  Use “Check for this condition every” to define how often Loggly evaluates the condition (e.g., every 1 minute, 5 minutes).

* Save and Activate -
  Save the alert configuration to start monitoring and receiving alerts.

Use Case Example - 
Detect brute-force attacks by triggering an alert when multiple authentication failures occur within a short time frame.
