Identification : who you claim to be, usually your username.
Authentification : prove who you say you are, password and other authetification factors. 
Authorization : based on your identity and authofication, what access do you have. 
Accounting : resources used are login time, data sent and received, logout time. 
Exemple of use of triple A : 
To have access to an internal file server. At first, I send a username and password to the VPN concentrator (Firewall), in itself it doesn't have those info so it sends it to the AAA Server, if it's approved the AAA server send that the credentials are approved to the Firewall, that gives then access to the internal server.
![[Pasted image 20260426185443.png|285]]Authetification system : you have to manage many devices, that we may never even see. How can we verify that a computer that eants to connect to our network is one that is allowed to do so ? Many cases put digitally certificate on the device, acces to the VPN from authorized devices and management software can validate the end device.