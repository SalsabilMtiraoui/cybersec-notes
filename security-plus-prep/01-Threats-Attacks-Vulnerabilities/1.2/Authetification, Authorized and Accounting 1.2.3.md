Identification : who you claim to be, usually your username.
Authentification : prove who you say you are, password and other authetification factors. 
Authorization : based on your identity and authofication, what access do you have. 
Accounting : resources used are login time, data sent and received, logout time. 
Exemple of use of triple A : 
To have access to an internal file server. At first, I send a username and password to the VPN concentrator (Firewall), in itself it doesn't have those info so it sends it to the AAA Server, if it's approved the AAA server send that the credentials are approved to the Firewall, that gives then access to the internal server.
![[Pasted image 20260426185443.png|285]]Authetification system : you have to manage many devices, that we may never even see. How can we verify that a computer that eants to connect to our network is one that is allowed to do so ? Many cases put digitally certificate on the device, acces to the VPN from authorized devices and management software can validate the end device.
Certificate Authority : trusted software or device (manage all certificate of our environment) that most organization maintain their own CAs. The organization creates a certificate for a device, and digitally signs the certificate with the organization CA's. 
Certificate-based authetification : CA certificate and device certificate compared to know if it's signed by the CA we trust. 
Authorization model : authentificated, but what do they have acces to ? users and and services -> data and applications, associatin individual users to acces rights does not scale. For that, we put an authorized model in the middle (roles, organizations...).
![[Pasted image 20260426195011.png|285]]To scale, we need an authorized model. Reduce complexity and creates a clear relationship between user and the resources. Administration is streamlined. Easy to understand the authoriztions, support any number of users. Exemple : shipping and receiving group created : 
![[Pasted image 20260426195142.png]]