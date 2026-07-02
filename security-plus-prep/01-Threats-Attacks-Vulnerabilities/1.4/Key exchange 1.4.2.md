It's a logistical challenge to share an encryption key accross insecure medium without physically transferring it ? 
- Out of band exchange : don't send the ymmetric key over the ''net'', exchannge irl would be courrier, in person ect... but on the internet it's ususally a in-band exchange, which means it will be in the network and need to protect the key with addictional encryption. **Use asymmetric encryption to deliver symmetric key**
Rela time encryption/decryption : need for fast security without comprimising the secuity. Share a symmetric session key using asymmetric encryption. Exemple : 
- Client encrypts a random (symmetric) key with a server's public key
- the server decrypt this shared key and uses to encrypt data -> this is the session key 
- Implement sesion key carefully : need to be changed frequently (ephemral) and be unpredictable
- 
## Symmetric key from asymetric keys 
Use public and private key crypto to create symmetric key (powerful math)
![[Pasted image 20260513153353.png]]


