
### Negotiations 
  
Negotiations are a key area of the global graph. Agents need to agree on
allowable mutations of the graph. For example, am I allowed to turn on
the lights? In this case, the mutation is something like

- `yourhome.lights.bedroomlight -> ON` 
- `yourhome.lights.bedroomlight -> OFF` 

For this mutation to be allowed, there must be a rule somewhere that says that a given agent (in this case mine), is allowed to perform this mutations. This negotiation is likely done offline, in which case you and I will agree that I can control this light, and you'll simply add the permission, or maybe I'll request permission, and your phone will pop up a notification asking if its okay.


Automated negotiations are more complicated, because agents need to understand what constraints the controlling agent places on the negotiation, and what types of constraints it knows how to handle. 
For example, a delivery time constraint needs to be understood by both AI agents, and the people operating these agents. 
They need to agree to this protocol, and have their owners agree that this a valid constraint to use in a negotiation. 
In other words, the digital constraint must have meaning that matters to the flesh and blood entities in control, and the AI entities must have rules describing what actual data changes when this constraint is satisfied. 
  

A time constraint constraint, at its simplest is a set of mutations that
must have occurred within a certain timeframe. For it to be useful,
there need to be trusted 3rd party time notaries that will digitally
sign that yes, transformation X (usb cable delivered), occurred at
4:34PM.


Returning to the USB cable example, while negotiating the contract, the
agents will add the constraint as part of a larger expression. If
constraint is satisfied, then $5 will be transferred from A to B. If it
happens within some acceptable delay, then $1 will. If it happens after
some time, then no money will be transferred and the whole transaction
will be voided.
  

This all sounds rather complicated for a person to manage, who simply
wants to buy a USB cable. Thats why the components of these constraints
and contract clauses must be both human and machine readable. It should
be easy for your AI Agent to explain what contract you're about to agree
to, but piecing together fragments of natural language, and potentially
informational graphics to explain whats about to happen.

### Home Automation

Home automation is a good example to illustrate the need for private
data mutation with real-world side effects. In the a sense of
side-effects, data mutation is limited to some applications. Turning on
a light securely is a very different story. Parts of the global graph
can be tired to physical systems.
  

Imagine visiting a friends house when they are not home. They've said
you're free to enter when they're gone, and make yourself at home. For
this to work, they must have first verified your digital identity. They
can then give you a pointer to the section of the graph that represents
their house. Since its global, you can potentially look it up using a
mapping application, that links the physical address to a sub-graph that
represents all the meaningful values in your house. They also sign a
statement that says you're allowed to mutate a few variables: The door
lock, but only after this Friday, for a period of one week. Also all the
lights, but not the sprinkler system or pool heating system. When you
visit, you can access the graph globally over the internet, or even more
efficiently and quickly by connecting to the WiFi. Speaking of WiFi,
they've already given you access to the WiFi using a similar mechanism.

### Mapping and Mashups 

A big part of our digital and physical lives is interacting and
navigating within 3D space, finding places to grab a coffee, getting to
a friends house, or mapping our run through the park. Right now these
activists can be performed via a variety of services such as Google
Maps, Yelp, Strava and more. However, if yo want to map your run against
a list of your favorite coffee shops, and then find a variation that
ends your run near a great cup of joe, you cant do this without the two
companies agreeing to export their data, and a 3rd company to make this
mashup. Likely the mashup includes yet another username and password, will send you
more spam, and may come at a cost.

With a graph of data representing both activities, making such a mashup
can be done by the person who owns the data, possibly using a general
purpose AI engine. Since all of this information is essential locations
with data about context (a coffee shop will have a link to a menu), and
a running track will also contain entries noting your pace, heart rate,
etc), they're already almost compatible. A general purpose program can
easily overlay the two.

What if this general purpose UI is kind of ugly? Luckily, since you own  the data,  you, your friend, or a business can create a new interface to the data.

### Social Networks, Group Messaging

I have not written this section yet.
