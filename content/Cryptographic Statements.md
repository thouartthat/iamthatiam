---
publish: True
---

### Cryptographic statements
Certain cryptographic statements are possible using [[Public Key Cryptography]]. A cryptographic statement is a statement expressed in [[Machine Readable Language|code]] that with [[reasonable probability]] proves someone in possession of a **private key** [[digital signature|signs]] and states a **statement** is true.

For Example:

``` JSON 
{"statement":
	{
		"owner": "email@example.org",
		"item_owned": {
			"name": "iPhone",
			"serial_number": 1234567,
		
		}
	 
	 },
	"signed_by": "shai7exahthiiFoh0iephie3soagiloo",
	"signature": "eemohdae8aez9uedie6ohZ3jieY1dahv"
 }
```

In this fictitious example, the statement says in [[Machine Readable Language|code]] that the something named `iPhone` with a serial number of `1234567` is owned by`email@example.org`. The signed by is a **public key** with a [[digital signature]]. If these were real values, one could verify that this full statement (including the signature and signed by) could only be produced with knowledge of the **private key** matching the **public key** `signed_by`.

If the **private key** is controlled, and exclusively known by a conscious entity, we can make the assumption that whatever conscious entity created and signed this document does testify to its accuracy. Of course people can lie, so whether it is [[What is True|true]] or not is a different story.

If conscious entities assign meaning to [[Machine Readable Language|machine readable]] documents, then lawful statements can be made in [[Machine Readable Language|code]].

