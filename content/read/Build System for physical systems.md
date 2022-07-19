---
publish: True
---

# Build System for Physical Systems
## "Recipes for Reality"
**Notice:** Like many documents on this website, this is a work in progress. If this interests you, and you wish to learn more please [[Connect with Me]].



A market place coupled with a digital-contract based build system and design language could allow each step of manufacturing a given good to be sold to the lowest bidder automatically, with a programmable tolerance for risk embedded into the contract.  
  
From a big picture point of view, imagine you want to build a widget that needs 3 plastic parts, P1, P2, and P3, as well as a circuit board, a battery and a some compliance stickers. If you can describe this product digitally, including how to build each part, and how to assemble them into sub and then final assemblies, with well defined acceptance criteria for each step, its not so hard to imagine putting up a request for quote for the entire project onto a marketplace, where each piece can be bid on separately.  
  
**Pricing Algorithms** The terms of the smart contract would show sliding price scales for each part, with an algorithm or function optimizing for the desired criteria (e.g. lead time, trust of vendor, price, tolerances, refund policy, secrecy, etc).

**Integrated Logistics**  
The marketplace would additionally have logistics/material handling included in the system. So if P1, P2, and P3 are all built by separate companies, potentially 3 different logistic providers could bid on moving the parts to an assembly facility that combines the parts into a sub-assembly.

**Compliance and Acceptance Criteria**  
  
The system would be flexible enough to allow arbitrary steps in the assembly process, including QC, compliance, shipping to customers, and potentially an entire business.  
  
For example, for a 3D printed part, one node/vendor can offer testing services. They will examine a part and cryptographically sign a statement that a given part matches some specifications 
  
**Web of Trust** An integral component of this marketplace is system for managing trust. Customers need to explain what level of confidence they require from vendors, and one or more ways to verify and select vendors matching their set of criteria.

Trust could be an explicit web, where your organization/smart contract
has pre-existing hard coded lines of trust extending to other entities.

Other entities can provide services directly, or can serve as mediators that help select other vendors. For example, an entity can be trusted at evaluating the quality of 3D printing vendors. If you trust it, you implicitly trust entities selected by it.

**Federated Identity and Information Platform** 
  
Taking this a bit further, the network can have a generic distributed consensus system, where any node can assert any expression, but the trust system ties a confidence to every assertion. For example, a node (A) can assert that node (B) can be trusted to evaluate 3D printed parts less than some dimensions and less that some tolerances.

It could also asset simpler statements like node C has GPS coordinates of XYZ, which might be useful for automatic drone logistics.

**Details and C Programming Metaphor**  
  
I'll stop writing for other audiences and just write for me/ a very technical audience for now.

Some ideas I want to touch on: 
  
Ethereum/block chain based smart contracts Build systems, (DAGS)

Acceptance criteria for Particular step succeeded

Selecting whether a given vendor can satisfy a given criteria 
  
If we start with a distributed C compiler/build system, we can start examining the beginning of the metaphor.

In a C based build system, you have a series of C and H files that eventually become a single binary or library. For simplicity in wording, I will only talk about static libraries for now. Dynamic libraries are essentially identical.

Basically header files assembled into the header for a C file, which is compiled into an object file.

So Header files ->  Header + C file -> Object File -> [ Object Files ] -> Static library

Static Libraries -> Executable

Also, each step has some compiler flags that encode the platform (where the code can run), and customizations to each step, as well as a set of symbols that affect pre-processing.

Since there are multiple compilers and formats for object files, this is another aspect of the build system that is complicated.

One of the static libraries can be libc, or some API so the static library can be run

Let's imagine that rather than happening on a single computer, this whole build process can happen over a P2P network, where any host can bid on compiling a file, linking libraries, or pre-processing header files.

For a node to successfully compile a file it needs to have a compiler that can input the version of C a file is written in, + headers in the same version of C, and support outputting in a particular object file format. For simplicity, we can use some kind of UUID system, where the compiler has a unique ID that can be a required part of the build process.

To simplify further, we can reduce the set of inputs to a build node to the source file, the compiler tag, the C version, and a set if pre-processor symbols.

Each node that wants to bid on a build will see the network broadcast a request for a node to compile

{ compiler tag: arm-none-eabi-gcc-4.2.7, speed: 100, price 1ETH} 
  
If a specific compiler tag turns out to be too restrictive, we could also have the requesting node publish a simple function, or expression that can be evaluated to determine if a specific node has the requested capabilities.

The responding vendor node can reply to the requester with its capabilities signed with its public key. The requester can then decide (using some kind of trust mechanism) whether it wants to submit the job to that node.

**Evaluation/Acceptance Criteria**  
  
Step in the build must have some kind of acceptance criteria to determine whether a given processing node actually did its job correctly. The AC could be true, i.e. always accept that a node performed the job correctly. This would either assume all nodes are trusted (either a private environment), or that the trust evaluation criteria passed.

Acceptance criteria will be a function or maybe (pure) that returns true if a given output is good. It could potentially evaluate tolerances and decided if theyre good enough. It may dependent on other acceptance criteria, or maybe use some built in properties and processing to evaluate the output.

A simple evaluator for a c compiler would be running the object through objdump and looking for a given format and the presence of some symbols.  It could also be to pass the output to another manual verifier.  Therefore it should be possible that one verifier sends the .o file via email to someone who decides if it passed or not, and replies with pass or fail in the email body. In this case the node that sends the email needs to be trusted, since if you tamper with it, there is no cryptographically/machine verifiable method of proving that a step was okay.

**Trust evaluation Criteria**  
  
Trust evaluation would operate very similarly to acceptance criteria evaluation. It would essentially be a function that must return true for a given node to be trusted.

However, trust doesn't necessarily have not be binary, and actually neither does the quality of output.

So trust selection must return one nodes that it can trust. This could be done by selecting the highest trusted peer (0 to 1) that is above also above a minimum trust threshold.

Trust could work using some web-of-trust algorithm, where you trust a list of peers/nodes explicitly (100%), and trust each every node as a function of the how much we trust the nodes that trust it.

So if I trust both of my friends 100%, and they each trust a different person 100%, maybe I should trust the 3rd party at 100% SO maybe I shouldn't trust my friends at 100%, and instead 90%, so someone they both trust could be some logarithmic sum of my trust \* their trust for all my peers.

Trust could also be delegated to a 100% trusted peer. This section needs much more thought.

**Cost evaluation** 
  
A part of this whole idea, is that you can ask the network for a collective bid on a job, and get back a price and lead time, and maybe some probability of success.

Therefore, we could demand 100% confidence, which requires all parts of the job to require 100% trust, which could be very expensive, or accept only 98% trust, but use some 3rd parties that can do complete parts of the job better.

The top level trust evaluator will decided how to evaluate the whole network. Therefore, you could have a company that you 100% trust to do the right thing, and you dont care how they evaluate all the sub-contracts for trust. It might be a 100% manual process.

The C build system metaphor is starting to break down pretty badly here.  
  
**Trust/Acceptance Criteria/Sub-contractor selection** We can also decided to delegate selection of sub-contractor/build nodes to a 3rd party manual node.

**Build Failures**

What do you do when a given node does not produce a passing artifact?  Should you try again, or select a new node?

**Build Recipe**

DAG of steps and (implicit/explicit intermediate artifacts) Acceptance Criteria function for final artifact.

Maybe separate AC for each intermediate artifact/sub-assembly, or maybe thats part of the top level AC
Node selection and evaluation function
Retry policy, price max

**Non C Examples** 

**Project: Requirements:** 98% or higher trusted 3D printing + design house Acceptance Criteria: Manually evaluated by 98% or higher verification company

- Design: plastic t-spoon set that looks like `attachment.jpg`, but with
`logo logo.jpg`. They should fit on a key-ring 1 inch in diameter, and be made
of food safe plastic.
- Acceptance Criteria: Sub-assembly AC
- Retry Policy
  