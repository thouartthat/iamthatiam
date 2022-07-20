---
publish: True
---

# Minimum Viable Product {#mvp}

This section describes the minimum viable "product", or the minimum amount of functionality needed to build something that is usable by people.

For an exchange to happen, there must be two people, and two items of value to be exchanged. 

A minimum viable exchange can be item for item, or item for [[Cryptocurrency]].

### Functional Requirements
- Agent Profile, and controlling principle profile (text and images, maybe some metadata)
- Ability to add "friends" or "peers" to local graph
- Ability to publish a list of goods or services you can provide
- Ability to browse a list of goods or services another is providing
- Ability to propose an exchange between you and another agent
- Ability to send and receive textual messages
- Ability to create new agents
- Ability to create new schemas (machine -> human readable translation layers)
- Directory
	- Ability to create a directory of people
	- Ability to add your agent to a directory
	- Ability to browse a directory
	- Reputation agent
- Reputation
	- Ability to host a "reputation" agent
	- Ability to join a reputation agent as someone who can be "rated"
	- Ability to leave a rating for someone at a reputation agent


### Implied Technical Requirements
- Local graph storage, editing, and querying
- Graph synchronization protocol 
- Schemas for:
	- Directory: (name -> public key, possible IP addresses, or onion addresses)
	- Reputation:
		-  (public key -> Reputation Document
		- Reputation Document: rating score, possible list of reviews)
		- Review
	- Permissions: possible standard schema for describing allowable mutations
	- Standard "agent"
	- Friend list
	- Profile
	- Item to exchange 
		- Possibly select a set of standard goods and services and build schemas for them, or make a super generic one
	- Exchange proposal
	- Message
- Frontend for:
	- listing items for sale
	- browsing directories
	- joining directories
	- searching for items to receive 
	- initiating exchanges
	- send messages
	- editing profiles
	- Writing reviews, reading reviews
	- Graph browsing and editing

### Optional Technical Requirements
- Optional: Onion routing




