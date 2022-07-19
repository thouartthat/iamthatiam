---
publish: True

---

# Public-Key Cryptography
Public key cryptography, in the general sense is the name given to certain concepts in discreet math that can be used for certain practical uses.

Public-key cryptography in the simple sense works with pairs of **keys**.

The **private key** is only known by the owner, and a **public** key which is shared with all other entities except the owner.

## Use Cases
Public-key cryptography can be used for a few purposes:

### 1. Sending Secret Messages

Given a **private key**, one can **encrypt** a message such that with [[reasonable probability]] it can only be decrypted by someone in possession of the **public key**.

Similarly, given a **public key**, one can **encrypt** a message such that with [[reasonable probability]], it can only be decrypted by someone in possession of the **private key**. 

### 2. Authenticating the sender of a message

Authentication here is defined as knowing that the sender of a message is in possession of the **private key**. 

The sender of a message can combine a message with the **private key**, and create a [[digital signature]] that shows that with [[reasonable probability]] the message was written by someone in possession of the **private key** that can be verified by anyone with the public key.

## References
[Public-Key Cryptography - Wikipedia](https://en.wikipedia.org/wiki/Public-key_cryptography)



