Windows Failed Login Detection 

Event ID: 4625

Try to perform multipule failed login attempts on windows vm using wrong password analysed the failed authentication events in Splunk.

Below are the findings of investigation -
Logon Type: 2
ComputerName=DESKTOP-JMN8F45

Account For Which Logon Failed:
	Security ID:		S-1-0-0
	Account Name:		narayana
	Account Domain:		DESKTOP-JMN8F45
Failure Information:
	Failure Reason:		Unknown user name or bad password.
	Status:			0xC000006D
	Sub Status:		0xC000006A

