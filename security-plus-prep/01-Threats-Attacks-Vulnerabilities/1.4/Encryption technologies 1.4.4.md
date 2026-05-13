## TPM trusted platform Module
FOR A SINGLE DEVICE
A specification for crypto functions, the cryptography hardware device.
- Cryptographic processor : random number generator, key generators
- persistent memory : unique keys burned in during manifacturing
- versatile  memory : storage keys, hardware configuration information, securely store BitLocker keys
- Password protected : no dictionary attacks

## HSM Hardware Security Module 
FOR PLENTY OF DEVICES, USUALLY CLUSTERED
For large environments, clusters and redundant power. Securely store thousands of cryptographic keys. High-end cryptographic hardware (plug-in card or seperrate hardware device)
- Key backup : secure stoarege in hardware
- Cryptographic accelerators : offloads that CPU overheard from other devices