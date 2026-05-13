Policies and procedures, software and hardware that are responsable for creating distributing managing storing et evoking digital certificates. Needs a lot of planning, it's a big big endeavor. Also refers to binding of public keys to people or devices, the certificate authority (CA), based on how to trust.

## Symmetric encryption 
A single shared key, encrypt with the key, decrypt with the same key, if it gets out you'll need another key. But it doesn't scale well, can be challenging to distribute. Very fast to use tho, less overhead than asymetric that's why still used.
- A secret key algorithm, shared secret
## Asymetric key
Two or more methametacally related keys. Both are create at the same time/same process. One of them is the private the other is the public. The private only one person can see it and use it, but the public one is seen and used by anyone. Only the private key can decrypt data encrypted witht the public key. you can't derive the private key from the public key even if they're mathematically related. 

## The key pair 
Asymmetric encryption : public key crypto. Key generation : build both the public and private key at the same time, lots of randomazation, large numbers and lots of math. Everyone van have the public key, but only Alice has the private one (ex: add a password to get it)
![[Pasted image 20260430100108.png]]
## Asymmetric Encryption
 Bob's laptop writes a text, use alice's public key and create cipher text can be sent to Alice. Anyone can see the ciphertext but without the private key of Alice, no one can get to the plaintext.
 ![[Pasted image 20260430100244.png]]
## Key escrow 
Someone else holds your decryption keys : your private keys are in the hands of a 3rd party, can be within your own organizazion. Can also be a buisiness arrangement, buisiness needing access to employee informations or governal agencies need to decrypt partner data. It's controversial but may still be needed
