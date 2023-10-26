# What is Networking?

Think of a network like a big web of connections, kind of like how you and your friends are connected through common interests. Networks are all around us, whether it's the transportation system in a city, the power grid, or simply how you chat with your neighbors or send mail.

In the world of computers, networks work the same way, but with tech devices like phones and laptops that talk to each other. These networks can be as small as just a couple of devices or as massive as including things like security cameras, traffic lights, and more.

Networks are a big deal in our daily lives, helping with things like collecting weather data, providing electricity, and even deciding who gets to go first at a four-way stop sign. Knowing about networks is super important in cybersecurity because they're a basic part of our modern world. You'll get to see a network diagram with Alice, Bob, and Jim later on, which will help you understand it better.

<p align="center">
<br/>
<img src="https://i.imgur.com/1cOghTe.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

Questions 1: What is the key term for devices that are connected together?

Answer: `Network`


<h2></h2>

# What is the Internet?

We've already seen what a network is – it's just a bunch of connected devices. Now, think of the Internet as a massive network made up of many smaller networks. In a simple example, imagine Alice wants to introduce her friends Zayn and Toby to Bob and Jim, but only Alice can speak their language. So, Alice acts as the messenger between the two groups.

Alice acts as a bridge, allowing two groups to communicate with each other, forming a new network.

<p align="center">
<br/>
<img src="https://i.imgur.com/U42ZFS9.png" height="90%" width="90%" alt=""/>
<br />

The Internet began with ARPANET in the late 1960s, funded by the U.S. Defense Department. It wasn't until 1989 when `Tim Berners-Lee` invented the World Wide Web that the Internet we know today, used for sharing information, was born.

Think of Alice's network of friends like computer devices. The Internet is like a huge version of this, connecting many devices.

<p align="center">
<br/>
<img src="https://i.imgur.com/VWpm9gC.png" height="90%" width="90%" alt=""/>
<br />

The Internet is like a big collection of connected networks. These networks can be either private or public. Devices on a network use labels to identify themselves.

<h2></h2>

Questions 1: Who invented the World Wide Web?

Answer: `Tim Berners-Lee`

<h2></h2>

# Identifying Devices on a Network

For a network to work smoothly, devices need to have names and unique identifiers, just like people. It's important to know who you're communicating with on the network, so names and identifiers help with that, much like how humans have `names` and `fingerprints` for identification.

People can change their names, but they can't change their fingerprints. Similarly, devices have two ways to identify themselves: an `IP address` and a `MAC address`, which is like a `serial number`. Just like our fingerprints, these identifiers help distinguish each device and maintain its unique identity.

<h2></h2>

<h3>IP Addresses</h3>

IP address is like a label used to identify a device on a network. This label can stick with the device for a while, and then it can be given to a different device without changing the label. It's a way to keep track of things on a network.

An IP address is a set of numbers that are divided into `four octets`. The value of each `octet` will summarize to be the IP address of the device on the network. This number is calculated through a technique known as `IP addressing & subnetting`. The key thing to remember is that each device on a network has a unique IP address, and you can't have the same address for two devices at the same time on the same network.

IP Addresses follow certain rules, called `protocols`, which help `devices talk` to each other in a `common language`. These rules are like the foundation of networking. Devices can be on either a `private or public network`, and this decides the kind of IP address they get: public or private.

A public IP address is like the address of a house on the Internet. It's how the device is found and recognized on the big worldwide web. On the other hand, a private IP address is more like a room number in a big building. It helps the device get noticed within a smaller group of devices.

Public IP addresses are given by your `Internet Service Provider` (or `ISP`) at a monthly fee (your bill!)

As more devices connect to the internet, it's getting harder to find available public addresses. So, IPv6 is a new iteration of the `Internet Protocol` addressing scheme to help tackle this issue.


<h2></h2>

<h3>MAC Addresses</h3>

Every device in a network has a special chip inside it called a `network interface`. This chip gets a special ID when it's made, kind of like a fingerprint. This ID is called a `MAC address` (`Media Access Control`), and it looks like a code made of twelve-character hexadecimal number, numbers and letters with colons in between.

<p align="center">
<br/>
<img src="https://i.imgur.com/8YCUufk.png" height="90%" width="90%" alt=""/>
<br />

MAC addresses can be `tricked or "spoofed,"` which means a device pretends to be a different device by using its MAC address. This can cause problems with security measures that trust devices on a network. For instance, if a firewall is set to only allow communication from the MAC address of an administrator, a spoofed device can make the firewall think it's the administrator, even when it's not. This can lead to security issues.

Cafes, coffee shops, and hotels often use MAC address control for their "Guest" or "Public" Wi-Fi. They do this to provide better services, like faster internet, especially if you're willing to pay extra for each device. 


<h2></h2>

Questions 1: What does the term "IP" stand for?

Answer: `Internet Protocol`

Questions 2: What is each section of an IP address called?

Answer: `Octet`

Questions 3: How many sections (in digits) does an IP address have? 

Answer: `4`

Questions 4: What does the term "MAC" stand for? 

Answer: `Media Access Control`

Questions 5: Deploy the interactive lab using the "View Site" button and spoof your MAC address to access the site.  What is the flag?

Answer: `THM{YOU_GOT_ON_TRYHACKME}`

<h2></h2>

# Ping (ICMP)

Ping is a basic tool for checking how well devices in a network can talk to each other. It uses special packets called `ICMP` to do this. For example, it can tell us if a connection between devices is working properly.

Ping also measures how long it takes for these special packets to go from one device to another and back. It does this by sending an `"echo" packet` and waiting for the target device to reply. This helps us understand how fast or reliable the connection is.

Pings are like saying "Hello, are you there?" to devices on a network, like your home Wi-Fi or websites. You can use this tool easily because it's already on your computer if you have Linux or Windows. To do a simple ping, just type `"ping" followed by an IP address or website URL`. 

<h2></h2>

Questions 1: What protocol does ping use?

Answer: `ICMP`

Questions 2: What is the syntax to ping 10.10.10.10?

Answer: `ping 10.10.10.10`

Questions 3: What flag do you get when you ping 8.8.8.8?

Answer: `THM{I_PINGED_THE_SERVER}`
