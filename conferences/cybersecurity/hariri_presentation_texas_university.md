# Cybersecurity

+ Def: security of cyberspace (protection of operations and assets)
+ Cyberspace: Information systems and networks
+ Possible failures: attacks, accidents ...
+ CIA: confidentiality, integrity ans availability
+ You are as secure as the weak point

## Chalenges:

+ Internet has became the first computing platform (access is opened)
+ Internet of Things -> increase the vulnerability (more doors opened)
+ BIG Data -> Huge amount of data received -> anyone can hide malicious code in this amount of data and it is hard to find it
+ Rich data types (malicious code inside images, music ... since they are only binary)
+ HTML with dynamic code
+ New technologies can bring new vulnerabilities
+ Attack sophistication and attackers knowledge (taking a leaked library of attacks from the government and use it) 
+ Insufficient number of workers

## Cloud security

+ It is more and more common to rent services from amazone, google and so on (without having the infrastructure).
+ Threats:
	+ Insider threat (the guys from amazone or google will access my data)
		+ Identity management, block unauthorized access
	+ Legacy systems (if there was a failure on your private system now it is in the cloud)
	+ Virtualization 
+ software as a service SaaS.
	+ The customer is not responsible for any failure
+ platform as a service PaaS.
	+ The customer only builds its application upon a platform (API) and integration and midware.
+ infrastructure as a service IaaS.
	+ The customer is responsible of everything but hardware (API). 
	
	
## Typical problems

+ routers default login/password
+ Encryption is the best way to secure data, but accessing and working with encrypted data is hard and consuming
+ Authentification: bio-markers recognizers improve security (face recognition) 
+ Many open source applications have been changed in order to introduce vulnerabilities ... so building your application on top of it makes it vulnerable ... specially with SQL databases (SQL injections)
+ When a vulnerability is patched and the company tells this, only a few users apply the patch ... but now the attackers know and can attack

## Solutions
+ Two philosophies:
	+ Preventions (firewalls, encryption)
	+ Intrusion detection :
		+ Signatures based: "I know what the bad guy is going to do"
		+ Most ani-virus work with this principle and sell you the databases
	+ Anomaly based:
		+ "I know what the normal is"
		+ High false positives  (false alarms -> problems)
		+ Development of specialists for each part of the system (fine grained tools to detect anomalies in very particular points of the system: one for wifi, one for bluetooth ....)
		+ Anomaly Behavior Detection 
		+ Need to detect footprints (features) to detect if it is malicious or not: 
			+ frequency of transitions (Denial of Service)
			+ sequence of transitions: the temporal transactions of the guy
 		
## Futur work	
+ Hijacking
+ Forensic analysis
+ Encryption
+ Tolerate the attack ... be robust enough (resiliance)
+ Operating system application (hot topic)

