---
publish: True
---

# Value Based Exchange

Value based exchange is the idea of exchanging value directly, without the need to use a medium of exchange such as [[money]]. A value based exchange can be compared to barter.

Computer technology, specifically the [[Great Global Graph|Great Global Graph]] and [[Build System for physical systems]], enable peers to describe the value they wish to receive, and the value they wish to give in a way that allows computer algorithms to match supply to demand directly, without the so-called "invisible hand" of economics.  

People wishing to interact and exchange value participate by creating a digital agent consisting of a **public key** **private key**, and then finding one or more other agents of the [[Great Global Graph]] to begin sending and receiving messages with. As the [[Great Global Graph]] is owned by no single entity, there is no single point of entry. Your agent's first interaction may be with an agent of a good friend who showed you now to install the App on your phone, or by finding a well respected agent with brand recognition. 

As you interact with other agents using your agent, you may discover interactions and exchanges you wish to participate in.  As you interact with the graph, you interact with many agents serving many purposes, many controlled by [[Real World]] conscious entities (other people). These agents serve as mediums bridging the purely digital world with the physical world. Your decision to interact with them is entirely up to you.

### Common Agent Types
 - Quality Control Agents
 - Escrow Agents
 - Reputation Agents
 - Contract Writing
 - Delivery and "Shipping"
 - Packaging
 - Assembly
 - Material Processing
 - Manufacturing
 - Raw materials

These will be examined further later.


## Examples

### Buying a USB Cable
Right now, almost all of the internet is a collection of pages, web
applications, and other contented written ostensibly for people to
consume. However, machine to machine communication is difficult. Imagine
how useful it would be to ask the internet: 

>Are there any local businesses that sell usb cables? Give me the cheapest one that has at least X reputation score, and wont take me more than 30 minutes to get?

1. Your AI Agent (think Siri on steroids) uses the shared physical mapping layer to
find business in your area. It in turn examines the data associated with each business, *asking* about the availability USB cables.

2. Your agent will also query **Delivery** agents for delivery time estimates, and filter out businesses that are too far away. 

3. Upon examining 5 stores, it finds one that sells the desired USB cable, and matches it with a delivery service that can get it in time.

4.  Your phone pops up a window showing you some options:
	1.  Free delivery by the store, but delivery will take 2 hours
	2. $5 delivery, in less than 30 minute by drone
	3. Free delivery by drone, but low reputation score
	
5. You select option 2, and 30 minutes later, the USB cable is dropped in your drone friendly mailbox.


### Apple for Banana: A technical Deep Dive
This example is written in a more formal style, and describes some of the steps and agents involved in greater detail.

An exchange occurs when two or more entities agree to, and then actually give and receive value. A simplified exchange between **A** and **B** is as follows:

1. **A** proposes to give one apple to **B**, in return for one banana
	The proposal consists of a few parts:
	- **A** optionally proposes to use a mediator, or escrow agent **M**, to verify the exchange happens
	- **A** specifies certain quality standards or metrics for the banana and apple to be exchanged
	- **A** proposes additional constraints, such as timeliness 
2. **B** either accepts the proposal, or modifies and and sets it back to **A** for negotiation
	- In this example, **B** proposes using a **Quality Control** agent to verify the physical items are as agreed upon before the tokens can be released from escrow
3. Upon mutual acceptance, **A** and **B** each create a [[Non Fungible Token]] representing the physical items.
	-  If desired, a request to a third party can be made to validate the quality of the physical banana. The third party is essentially stamping the [[Non Fungible Token|NFT]] with its reputation, asserting that according to it, the banana or apple is good
4. The NFTs are entered into escrow, with a digital contract stating that the tokens are not to be released until the agreed upon conditions are met. In this case, after the agreed to **Quality Control** agent asserts the physical items are delivered as described, the [[Non Fungible Token|NFT]]s are released to the new owners.
5. In the case of a dispute, quality control failure, or other reason, the tokens are returned to original owners.

#### Caveats
This is a relatively simple exchange. More complex conflict resolution can be put into the contract. For example, what if the banana is delivered correctly, but the apple arrives damaged. In this case, the banana token should be delivered to the **A**, and a debt created to show that **A** did not deliver the banana as agreed upon.  

The contract could also have penalties for late delivery, so a late deliver may incur a debt of one apple + a late fee of **X** per day the apple is late, with an escape clause saying that if **A** decides to exit the contract, **A** agrees to give **B** some other value for the inconvenience.

The actual material handling could be handled by a sub-contract with a "shipping" agent. The contract can have provisions for numbers of retries before failing.


## Solar Panel Installation
Let's say you'd like solar panels installed on your roof with a 10kWh battery, and sine wave inverter capable of supplying 5kW continuous, 10kW peak power.

1. You find an agent that provides a contract template for solar installation you like
2. You fill in the details of the contract
3. You "ask" the network how to fulfill the contract.
4. The network examines some or all possible ways to fulfill the contract, and gives you the option to select one
5. You are overwhelmed, so you delegate another agent to select the the right option. A nice human calls you on your phone and helps select what you actually need
6. The contract is "signed", and all the venders needed to fulfill it jump into action
7. At some point in the future your solar panels are installed just as you'd like

### Detailed Breakdown
Let's break this down a bit. Specifying exactly how to install solar fully in [[Machine Readable Language|code]] is a bit tricky. 

#### 1. Solar Contact Agent
The first step here is finding a digital contract that has agreed upon meaning in the [[Real World]]. For most people, they will turn to a friend, or a business that specializing in creating solar installation contracts. Their job is to turn the messy human readable specifications into machine readable code. They might have a nice form to fill out, or a you may call someone who will ask you questions and help fill out the form. The output of this will be a a [[smart contract]] that can be directly bid on by other agents on the [[Great Global Graph]].

You are trusting the people responsible for this agent that their smart contract is valid, unambiguous, and will result in the desired [[Real World]] changes, in this case, having solar installed correctly.

#### 2. Filling in the Contract
If you chose to fill out the contract directly, there will be certain inputs that need to be provided by you. For example:

 - what reliability guarantees do you want? 
 - Do you need an inverter? 
 - Does it need to be a "Pure sine wave" inverter?
 - What kind of panels do you need?
- Do they need to be installed by a professional, or will you do that yourself?
- If installed professionally, what kind of roof do you have? 
- How much will you pay, or what will you exchange for the solar installation?
- When do you need it?
- What kind of guarantees on timeliness do you need?

These inputs will become values in computer code. 

#### 3. Asking the Network to Fulfill the Contract
Once the contract is drafted, your agent will look for agents that can potentially fulfill the contractual obligations. 

This is where most of the "magic" happens.

Let's say the contract is somewhat as follows:

```JSON
{
	"needed-by": "10 Oct 2022",
	"requirements": {
		"contract-schema": "@open-solar-group/basic-solar",
		"componenents": [
			{"type": "inverter",
			 "specs": {
				"peak-power": "10000W",
				"continuous-power": "5000W",
				"min-temperature": "0C",
				"max-temperature": "60C",
				"phases": 1,
				"voltage": 120,
				// ETC
			 },
			 {"type": "solar-charging",
			   "specs": {
					"watts": "500",
					"system-voltage": 48
			   }
			 },
			 {"type": "battery",
			  "specs": {
				"capacity": "10kWh",
				"system-voltage": 48,
				// etc
			  }
			}
		],
		"installation": {
			"roof-type": "shingles",
			}
		// etc
	
	}
	
 }


```

Your agent will shop this contract around, and look for other agents that claim they con fulfill it. However, your agent need not find a single vender to fulfill the entire contract.

The agent may have functionality to look at each requirement separately and ask the graph for each component separately. For example, it can look at the `solar-charging`  component and look at a set of recipes for `solar-charging` and find that there are 100 different ways to satisfy this requirement. For example:

 - A single 500 watt panel, and a single MPPT to convert it to 48V
 - Two 250 watt panels, and a single MPPT to convert it to 48V
 - Multiple MPPTS

Each of the options can be sorted based on different criteria, and a the "optimal" solution selected. Since these selections are often highly technical, it may be advisable to delegate the decision to a trusted agent controlled by someone in the [[Real World]].

#### 5. Delegating to someone with Technical Knowledge
If the number of ways to fulfill a contract are overwhelming, it may be advisable to bring a trusted expert into the equation. A contract may be extended to delegate authority to deciding how it is fulfilled to a particular agent. 

#### 6. Signing the Contract
Once you are happy with the option you selected, you accept a particular solution to the contract, and it is set into motion.

Each step of the contract may have subtleties encoded into it, such as what to do if a vendor flakes, how to select alternate vendors, allowable delivery providers, etc. 

#### 7. Contract Fulfillment 

After the contract is signed, different agents will go out and fulfill their part of the contract. Parts may be shipped to different locations for processing, people will show up at your house and inspect your roof, and more.

#### Caveats 
This example is full of caveats and assumptions. The details of every different contract and sub-contract are not fleshed out. I do not claim to have the answers to how to do so. These require domain specific knowledge I don't have .

That being said, I believe that with time, by starting small, and using certain primitive building blocks we can build a system that allows you to ask, and then receive what you value. 


## Note about Money

I do not claim that money should not be used, simply that exchange should be as direct as possible, and not regulated by any authority with violence. If people wish to use some form of "currency" or "money", such as gold as a common value to exchange, this does not conflict with the ideas of a value based exchange.



## Types of Agents
Throughout these examples, there have been certain assumptions about certain agents existing and being available for interaction.  They are listed again below:

### Quality Control
Quality control agents are controlled by people wishing to offer their services as guarantors of quality. Let's say you'd like to inspect fruit for ripeness. You can offer your services as a quality control agent.

Then other agents with requirements on ripeness can sub-contract out the verification of ripeness to you, via your agent. 

For this to work, the **Ripeness Quality Control** agent, buyer and seller must agree to a mapping from a [[Machine Readable Language]] to a lawfully meaningful definition of ripeness, and then encode this in their digital contracts.

If they do so, then a **Quality Control Agent** can testify to the ripeness of a fruit, represented by an [[Non Fungible Token|NFT]], and do so by applying a [[digital signature]] to it.

**Quality Control** agents can also testify as the the "quality" of a delivery, verifying that some physical object did in fact arrive at some location undamaged. 

### Escrow
An escrow agent is a controlled by someone who is mutually trusted to hold property until certain conditions are met. 

If two people are performing an exchange, and don't fully trust each other, they may chose to put their property into escrow until mutually agreed upon quality control agents testify to the quality of the property in escrow, or that the physical items were delivered as per a contract.

### Reputation
Reputation agents are controlled by people who will testify as the the reputation of other agents. These are the basis of creating various digital reputation scores. Think of reputation agents like Yelp, or Google with associated reviews of businesses. 

The [[Great Global Graph]] and [[Value Based Exchange]] does not require these to exist, nor enforce a particular type of reputation. You can trust your friend as a reputation agent, or trust yelp. The choice is yours. 

### Contract Writing
Writing digital contracts that interact with a myriad of agents and standards is technical work. As not everyone wishes to dive into [[Machine Readable Language|code]] just to buy food, there will be certain agents trusted with translating human readable language into code. 

You may pay a service to respond to text messages, and then write contracts to fulfill requests.

You may also pay a service to simply write contract templates that you may wish to use directly. They may provide human fillable forms that in turn generate smart contracts.

### Delivery and Shipping
Physical items must be moved from location to location. Agents controlled by people in the shipping and receiving business may fulfill contracts that result in physical items moving from one location to another in the [[Real World]].

### Schema and Standards
For any of these agents to be useful, the people interacting with the agents must agree what the [[Machine Readable Language|code]] means in the [[Real World]].  People are free to make as many different mappings between [[Machine Readable Language|code]] and the [[Real World]], and some people will likely create a set of standard mappings or *schemas*  that are widely adopted. There can also be competing standards and schemas with different pros and cons, and again it's up to each conscious entity to decide what schemas to use, using whatever decision making process is right.

### The Sky is the Limit 
For now, I will leave the following examples unelaborated. Anyone can provide any physical item, or any service they wish to. As long as a schema exists, someone can make an agent that can negotiate and provide a good or service matching the schema. Reputation scores and reputation agents can help mitigate some amount of anti-social behavior. Any real harm caused must be resolved in the [[Real World]]. People will need to grow up and [[Do Inner work and share]].

As **simple** exchanges begin to happen, more and more complex schemas will emerge. It will become possible to describe every step of manufacturing a car, in a single data structure, including 

 - Material Processing
 - Manufacturing
 - Raw materials
 - Quality Control
 - Tolerances
 - Testing
 - Assembly

The complexity is huge, because the complexity of modern life is huge.  It can be made explicit and open to optimization by describing it all in [[Machine Readable Language|code]]. As people interact as peers, and building the knowledge graph of life, we may sere a world of abundance and peaceful cooperation.


![[Value Based Exchange MVP]]