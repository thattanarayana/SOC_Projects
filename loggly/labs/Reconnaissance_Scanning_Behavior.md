					                                          -: Reconnaissance / Scanning Behavior :-

As part of exploring the Loggly tool, I simulated reconnaissance/scanning activity on a Linux machine to analyze log patterns and configure alerting mechanisms.

Simulation Command -
for i in {1..30}; do logger "Connection attempt from 10.0.0.$i"; done

Log Analysis -
-> Search Parameter Used: Connection attempt
-> This filter helped identify repeated connection attempts across different IP addresses.
-> The generated logs simulate reconnaissance activity such as network scanning or probing attempts.

Alert Configuration -
-> Created an alert based on the above search query.
-> Configured the alert to trigger when multiple connection attempts are detected within a defined interval.
-> This helps in early detection of potential scanning or suspicious activity.

Note :- -> Capture images attached under the labs folder for eveidence purpose.
-> Images are in the name of "Reconnaissance_Scanning_Behavior_1 & Reconnaissance_Scanning_Behavior_2".
