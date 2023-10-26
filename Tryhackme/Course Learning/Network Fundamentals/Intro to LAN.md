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
