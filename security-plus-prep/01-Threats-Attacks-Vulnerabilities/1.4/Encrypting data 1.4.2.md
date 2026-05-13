Potet stored data on storage devices. ''Data at rest'' in the hardware (SSD, USB, Cloud Storage et...). Full disk and partition, volume encryption (BitLocker, FileVault...). File encryption : EFS = encryption file system, third party utilities for it to encrypt a single file/folder in the advanced attributes.

## Database encryption 
- protecting data storage and the transmission 
- transparent encryption, encrypt AL database info with a symmetric key 
- record-level encryption: encrypt individual columns/files, use seperate symmetric keys for each column. 
Eemple : display name, surname, but encrypt the column of the security number 
![[Pasted image 20260513143637.png|387]]
## Transport encryption 
- Protect the data traversing network (being on the interner basically)
- Encrypting in the application, browsers communicate through HTTPS
- VPN (virtual private network) : encrypt all data transmitted over the networkregardless. 
	- Client-based VPN using SSL/TLS
	- Site-to-site VPN using IPsec

## Encryption Algorithm 

Both sides need to use and have the same. There's many ways to encrypt data, the specific ''right'' formula must be used durint encryption and decrypting. Algorithm decided BEFORE encrypting data and usually the details are hidden fom the end user. Algorithms have different advanges and disadvanteges (speed, complexity. security level...)

Advanced Encryption Standard AES, DES = data encryption standard, exemple of the difference (no need to know by heart)
![[Pasted image 20260513144327.png]]
## Cryptographic keys
the algorithms are usually public, the algorithm is very known and the more it's seen the more it's trusted. The major unknown info is the key, without the key we can't reverse engineer. Knowing a knock door doesn't help to open it without a key. The key determines the kex : encrypted data, the hash value or digital signature. That's why it's so important to keep the key secret 

- Key lengths : larger keys tend to be more secure from brute force. 128-bits or larger are common, with time those numbers are getting bigger. 
- Asymmetric encryption : complex calculations of prime numbers, larger than the symmetric encryption and common keys are 302 bits or longer
**Key Stretching**: Make a weak key strong by addind processes to it, like hash a password, hash the hash of the password... brute forces attacks would need to reverse each of those hashes, making them waste more time and energy even if the key is small and weak.