#  Introducing LAN Topologies

Local Area Network (LAN) Topologies

Over time, people have tried out different ways to set up their computer networks. When we talk about "topology" in networking, we're basically talking about how the network is organized or arranged. Now, let's talk about the good and not-so-good things about these different network designs.

<h2></h2>

<h3>Star Topology</h3>

In a star Topology, each device connects directly to a central device are individually connected via a `switch or hub`. This type of network is very common and is popular because it's `reliable` and can grow easily, even though it can be a bit `expensive`.

In this setup, when you send information to a device, it goes through a central device that's connected to it. 

Advantages: 

- This `setup costs more` because it needs `extra cables` and special equipment. But even though it's pricier, it has some big benefits. It's `super flexible`, which means you can `easily add` more `gadgets` when you need to `expand` your network.

Disadvantages:

- As the `network` gets `bigger`, it needs `more maintenance` to work properly. But the more you depend on maintenance, the `tougher` it is `to fix` problems. Even though the star setup is `less likely to fail`, it `can` still `go wrong`. For instance, if the `main device` that connects everything `stops working`, all the `other devices` `can't` `talk to each other`. Luckily, these `main devices` are usually pretty `tough`.


<p align="center">
<br/>
<img src="https://i.imgur.com/XRKxIXr.png" height="90%" width="90%" alt=""/>
<br />

<p align="center">
<br/>
<img src="https://i.imgur.com/1loe5YJ.png" height="90%" width="90%" alt=""/>
<br />



<h2></h2>

<h3>Bus Topology</h3>

In this setup, we have `one main cable`, like the `trunk of a tree`. `Devices` are `connected` to this `cable`, kind of like `leaves grow from branches on a tree`.

Advantages:

- Bus Topology are `one of the easier` and `more cost-efficient` to `set up` because they `don't require` `expensive cables` or `special equipment to connect devices`.

Disadvantages:

- When `all data` for each device `travels on one cable`, it can `slow down` and create a `traffic jam` if multiple devices want data at the same time. This can make it `hard to figure out` `which device` is having `problems` because they all `share same path`.

- Another problem with the Bus Topology is that it `lacks a backup plan` if something goes wrong. This happens because there's a `single weak point` in the `main cable`. If this `cable breaks`, `devices can't talk` to each other anymore.

<p align="center">
<br/>
<img src="https://i.imgur.com/jVD57JO.png" height="90%" width="90%" alt=""/>
<br />

<p align="center">
<br/>
<img src="https://i.imgur.com/syQYAKc.png" height="90%" width="90%" alt=""/>
<br />


<h2></h2>

<h3>Ring Topology</h3>

The ring topology, also called `token topology`, is a network `setup` where `devices` like computers are `linked in a circle`. This means there's `less need` for lots of `cables` and less reliance on `special equipment`, constrast to what's needed in a star topology.

The `data travels around in a loop` `until` it gets to where it's `supposed to go`. Devices on the loop help pass the data along. What's cool is that a device will `only send data it gets from another device` when it `doesn't have any of its own` to send. `If it has its own` data to send, it `sends that first` before passing on someone else's data.

Advantages:

- In this setup, `data moves in only one direction`, making it `easy to fix problems`.

- There are `fewer traffic jams` compared to a Bus Topology because a lot of `data isn't moving all at once`.


Disadvantages:

- `Not the most efficient way` for data to travel because it `might have to go through lots of devices` before it reaches where it's supposed to.

- The way it's set up means that if a `cable gets cut or a device breaks`, the `whole network stops working`.

<p align="center">
<br/>
<img src="https://i.imgur.com/Z0eu5IF.png" height="90%" width="90%" alt=""/>
<br />

<p align="center">
<br/>
<img src="https://i.imgur.com/wQjRk3H.png" height="90%" width="90%" alt=""/>
<br />


<h2></h2>

<h3>What is a Switch?</h3>

`Switches` are like `traffic controllers for a network`. They collect lots of gadgets like computers, printers, and other network stuff and `plug them into their special slots`. These switches are often used in big networks like at companies, schools, or large places with many gadgets. They have different slots (4, 8, 16, 24, 32, 64, etc.) where all these gadgets can connect.

`Switches` are way `smarter` than hubs or repeaters. They `know which device is plugged into which connection`. So, when they get a message, they `don't shout it to everyone` like a hub would. Instead, they `send it directly to the right person`. This makes the network `faster and less crowded`.

Switches and routers can link up with each other, which makes the network `more dependable` because it gives data more than one way to go. If one path has a problem, `data can use a different route`. It `might slow things down` a bit, but the `network keeps working`, which is better than it not working at all,  `increases the redundancy` (the reliability).

<p align="center">
<br/>
<img src="https://i.imgur.com/SoFIRCQ.png" height="90%" width="90%" alt=""/>
<br />


<h2></h2>

<h3>What is a Router?</h3>

A router links different networks and shares information between them. It's like a traffic cop for data, deciding where it should go.


Routing is like giving directions to data so it can find its way across networks. It's all about making a `road for data to trave`l on and reach its destination safely.

<p align="center">
<br/>
<img src="https://i.imgur.com/3Jsl2Hg.png" height="90%" width="90%" alt=""/>
<br />


<h2></h2>

Question 1: What does LAN stand for?

Answer: `Local Area Network`

Question 2: What is the verb given to the job that Routers perform?

Answer: `Routing`

Question 3: What device is used to centrally connect multiple devices on the local network and transmit data to the correct location?

Answer: `Switch`

Question 4: What topology is cost-efficient to set up?

Answer: `Bus Topology`

Question 5: What topology is expensive to set up and maintain?

Answer: `Star Topology`

Question 6: Complete the interactive lab attached to this task. What is the flag given at the end?

Answer: `THM{TOPOLOGY_FLAWS}`

<h2></h2>

# A Primer on Subnetting

`Networks` come in `all sizes`, from `small to big`. `Subnetting` is like `cutting a big cake` into smaller pieces. Imagine you have a limited cake, and lots of people want a slice. `Subnetting` is `how you decide who gets how much cake`, making sure everyone gets their fair share of this "cake."

Network admins use something called `subnetting` to `organize and designate` specific sections of a `network` for this purpose.

`Subnetting` is like `dividing` a big group of friends into smaller groups. The number of friends in each group is decided by something called a `"subnet mask."` This mask tells us how many friends can be in each group.

An `IP address` is made up `4 sections` called `"octets"`. The same goes for a `subnet mask` which is also represented as a `number of 4 bytes (32 bits)`, ranging from `0 to 255` (0-255).

<p align="center">
<br/>
<img src="https://i.imgur.com/V3xihxM.png" height="90%" width="90%" alt=""/>
<br />

Subnets use IP addresses in three different ways:

- Identify the network address
- Identify the host address
- Identify the default gateway

<p align="center">
<br/>
<img src="https://i.imgur.com/rLXEdSZ.png" height="90%" width="90%" alt=""/>
<br />

Subnetting provides a range of benefits, including:

- Efficiency
- Security
- Full control


<h2></h2>

Question 1: What is the technical term for dividing a network up into smaller pieces?

Answer: `Subnetting`

Question 2: How many bits are in a subnet mask?

Answer: `32`

Question 3: What is the range of a section (octet) of a subnet mask?

Answer: `0-255`

Question 4: What address is used to identify the start of a network?

Answer: `Network Address`

Question 5: What address is used to identify devices within a network?

Answer: `Host Address`

Question 6: What is the name used to identify the device responsible for sending data to another network?

Answer: `Default Gateway`


<h2></h2>

#  The ARP Protocol

Devices can have two identifiers: A `MAC address` and an `IP address`.

`ARP protocol (Address Resolution Protocol)`, is the technology that is responsible for allowing devices to identify themselves on a network.

`ARP protocol` `allows` a `device to associate its MAC address with an IP address` on the network. Each device on a network will `keep a log` of the MAC addresses associated with other devices.

When devices want to talk to each other, they shout out to devices in the network to find the device that it wants to talk to. They use the ARP protocol to get the MAC address (like a digital fingerprint) for the conversation.

<h2></h2>

<h3>How does ARP Work?</h3>

Every device in a network `keeps` a kind of `memory` called a `cache`. In the `ARP protocol`, this memory `stores` the `names of other devices` in the network.

In order to map these two identifiers together (IP address and MAC address), the ARP protocol sends two types of messages:

- ARP Request
- ARP Reply


When an `initial device` `sends` an `ARP request`, it's like shouting out to everyone on the network, `asking` if anyone has a `specific address`. If another device has that address, it replies to it with an `ARP reply` to the initial device to acknowledge this. The `initial device` will now `remember` this and `store` it within its `cache (an ARP entry)`. 

<p align="center">
<br/>
<img src="https://i.imgur.com/0bNGMUY.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

Question 1: What does ARP stand for?

Answer: `Address Resolution Protocol`

Question 2: What category of ARP Packet asks a device whether or not it has a specific IP address?

Answer: `Request`

Question 3: What address is used as a physical identifier for a device on a network?

Answer: `MAC Address`

Question 4: What address is used as a logical identifier for a device on a network?

Answer: `IP Address`


#  The DHCP Protocol

`IP addresses` can be `given` to devices in `two ways`:

- Someone typing them in
- more commonly, by a `DHCP (Dynamic Host Configuration Protocol) server`

When a `new device joins` a `network` and `doesn't have an IP address` yet, it `sends out` a `request (DHCP Discover)` to `see` if any `DHCP servers` are `on the network`.

-  New device asks if there is any server that can give it an IP address.

The `DHCP server` then `replies back` with an `IP address the device could use` `(DHCP Offer)`.

- The server says, "Sure, here's an IP address you can use." 

The `device` then `sends a reply` confirming it `wants` the offered `IP Address` `(DHCP Request)`

- The device then says, "Okay, I'll take it!"

Lastly, the `DHCP server sends` a `reply acknowledging` this has been completed. The device can start using the IP Address `(DHCP ACK)`.

- The server says, "Great, you're all set!". The device can use that IP address to connect to the network.

<p align="center">
<br/>
<img src="https://i.imgur.com/M9rLhee.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

Question 1: What type of DHCP packet is used by a device to retrieve an IP address?

Answer: `DHCP Discover`

Question 2: What type of DHCP packet does a device send once it has been offered an IP address by the DHCP server?

Answer: `DHCP Request`

Question 3: Finally, what is the last DHCP packet that is sent to a device from a DHCP server?

Answer: `DHCP ACK`

