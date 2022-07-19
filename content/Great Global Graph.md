---
publish: True
---

# Great Global Graph Technical Overview
  
## Premises

- People, companies, and more should be able to own their data
- People should be able to interact securely and give other entities
access to see or modify their data.
- The application layer should be independent and readily replaceable
- Some data should live in a persistent immutable store
- Modifying (or maybe even reading?) some data can have side effects
-   This is relevant for the physical world, which encompasses mutation of variables
    that have real world consequences, e.g. changing temperature,
    unlocking a car, and more

Applications can be made by describing valid mutations of the data,
rather than hiding the business logic behind servers or code.
Mutations should be possible without requiring global consensus.


**Brief Technical Overview**  

In technical terms, the Great Global Graph is a distributed data structure, where each peer stores information locally, structured in a private data structure, and selectively maintains relationships to other private data structures. Agents participating in the graph can constrain mutations on a subset of their data-structure by making [[Cryptographic Statements]] on a [[blockchain]]. 

## Examples



## Core Technologies
- [[Distributed Hash Table]]
- [[blockchain]]
- [[digital signature]] and [[Public Key Cryptography]]
- [[Onion Routing]]