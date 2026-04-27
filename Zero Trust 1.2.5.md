Many networks are relatively open on the inside, once you're through the firewall there are few seurity controls.
The combo : something you have + something you know + something you are
Zero trust is a holistic approach to network security, covers every device, process and person. Nothing is inhertly trusted and everything must be verified : multi factor authentification, encrypion, more firewalls, monitoring and analytics. 
Planes of operation : split the network into functional planes, appries to physical virtual and cloud comonents. 
Data plane : process the frames packets and netork data, processing, forwarding trunking, encryping NAT. 
Control plane : manage the actions of the data plane, define poliies and rules, determines how packets should be forwarded, routing tables, session tables, NAT tables.
Extend the physical architecture : physical switch, how to break the plane ? (works with virtual too)
![[Pasted image 20260427140241.png]]
Controlling trust : adaptive identity, we examine qho is asking. Look at the source and the requested resources, multiple risk indicators : relationships to the organization, physical location, type of connection, IP address ect... make the authentification stronger if needed !!
Threat scope reduction, decrease the number of entry points. Policy driven access control : combine adaptive identity with predefined set of rules.
Security zones : security is more than one to one relationship, broad categorizations provide a security related foundation. 
![[Pasted image 20260427140643.png]]
Policy enforcement point : subjects and systems that are communicating throught the network are gonna be checked. It's like a gatekeeper.
The policy decision point is the result to examine the authentification to ddecide if it's allowed or not.
![[Pasted image 20260427140838.png]]
![[Pasted image 20260427140857.png]]
Zero trust final model : 
![[Pasted image 20260427140919.png]]
