# Routing

## Dynamic Routing 

### Dynamic Routing Protocols

Listens for subnet information from other routers that is closed
- Sent from router to router
- Build a table within the router > Send their own advertisement out to those routers that are nearby.

Provide subnet information to other routers
- Tell other routers what you know

Determine the best path based on the gathered information
- Every routing protocol has its own way of doing this

When network changes occur, update available routes
- Different convergence process for every dynamic routing protocol

#

### Which routing protocol to use?

What exactly is a route?
- Is it based on the state of the link? - Up or down?
- Is it based on how far away it is? - number of hops or speed of communication?

How does the protocl determine the best path?
- Some formula is applied to the criteria to create a metric
- Rank the routes from best to worst

Recover after a change to the network
- Convergence time can vary widely between routing protocols
  - Some can quickly identify outage, quickly redefine routing tables to work around that outage.
 
Standard or Proprietary Protocol?
- OSPF (Open Shortest Path First) and RIP (Routing Internet Protocol) are standards
- EIGRP (Enhanced Interior Gateway Routing Protocol) are Cisco Proprietary

#

### Distance-Vector Routing Protocols

Information Passed between routers contain network details:
- How many hops away is another network?
- The deciding vector is the distance

Usually Automatic
- Relatively little configuration

Good for smaller Networks
- Doesn't Scale well to very large network

Example of Distance Vector Routing Protocol:
- RIP (Routing Internet Protocol)
- EIGRP (Enhanced Interior Gateway Routing Protocol)


![image](https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/c00ebd50-d8ca-4ced-a54c-205243206c48)

- Sam wants to send traffic to Jack > Since Distance Vector Rounting recommends the lowest hop, it will take the 100 Mbps path. Even tho R2 to R3 is 10x faster than R2 to R1 but with 2 hops R2 to R3 to R1.

#

### Link-State Routing Protocol

Information passed between routers is related to the current connectivity
- If it's up and performs high speed, you can get there.
- If it's down, you cannot.

Consider the speed of the link
- Faster is always better
- Might take additional hops but ultimately, you will transmitting that traffic with faster network.

Very Scalable
- Used most often in large networks

OSPF (Open Short Path First)
- Large, scalable routing protocol

#

### Hybrid Routing Protocols

Combine both Link State and Distance Vector with their advantages
- Not many examples of hybrid routing protocol

Good Example of Hybrid Routing Protocols:
- BGP (Border Gateway Protocol)
- Determines route based on:
  - Paths, network policies or configured rule-set.
 
#

# Routing Techonologies

## Routing Table

A list of directions for your packets 
- A table with many routes to your destination
- Packets stop at every router and ask for directions, the direction on where the packet go is depends on a routing table.

Every router has a list of directions:
- When packet is inbound, the router evaluates the destinatoin IP Address and determines the best route based on the list of routes.
- Packet makes to next router and performs the same lookup to its routing table and determine the best route.

Routing table in routers, workstations and other devices
- Every device need directions

#

## Hop

Hop
- A packet passes thru router.

Next hop
- Destination address of the next Gateway.

A Router doesn't need to know how to get everywhere
- Just needs to know how to get out of here
- **Default route** handles everything not specifically listed
  - If no path work, it will look at the default route to get to the destination.

Time to live in IPv4, Hop limit in IPv6
- Avoids a packet looping forever: Routing loop
- A counter inside IPv4 packet, everytime it hits a router, number decreases by one.
  - Once number gets to zero, the packet is discarded by the router to aviod routing loop forever.

#

## Configuring Next Hop

Every router needs to know where traffic should be sent
- Your packet is always asking for directions.

Router with incorrect next hop will result in a routing problem:
- data will go the wrong direction
- A routing loop is easy to create

Dynamic Routing Protocol 
- The router determines the best route

Static Routes
- Configuring manually by telling the router where the destination should be

#

## Default Routes

A route when no other route matches 
- The gateway of last resort

Route used when nothing else in the routing table match
- Instead of simply dropping that packet because no destination for the route, you will instead send it out this default connection.

Remote site may have only one route
- Go that way -> rest of the world
- Destination of 0.0.0.0/0

Can dramatcially simplify the routing process
- Works in conjunction with all other routing methods.
  - Router might be configured with dynamic routing but might also manually adding a default route to cover any of the instance where specific route can't reach.
 
#

## Routing Metrics

Each routing protocol has its own way of calculating the best route
- RIPv2, OSPF, EIGRP

Metric values are assigned by the routing protocol
- RIPv2 metrics aren't useful to OSPF or EIGRP

Use metrics to choose between redundant links
- Choose the lowest metric, 1 is better 2.

#

## Administrative Distances

What if you have two routing protocols and both know about a route to a subnet?
- Two routing protocols, two completely different metric calculations
- You can't compare metrics across routing protocols
- Which one do you choose?

Administrative Distances = Tie breaker
- Used by the router to determine which routing protocol has priority

#

## Managing network Utilization

Many different devices
- Desktop, laptop, VoIP Phone, mobile devices

Many different applications
- Mission crticial applications, streaming video, steaming audio

Different apps have different network requirements
- Voice is real time
- REcorded streaming video has a buffer
- Database application is interactive

Some application are more important than others
- Voice Traffics needs to have priority over YouTube

#

## Bandwidth Management - Traffic Shaping

- Traffic Shaping, packet shaping
- Control by bandwidth usage or data rates
- Set important applications to have higher priorities than other apps.
- Manages the Quality of Service (QoS)
  - Can configurate inside Routers, Switches, firewalls, QoS devices.


![image](https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/4672ceca-f464-4775-b5e8-56044c6dadc7)



Key takeway:

- Dynamic Routing = Sending traffics from one router to another and deciding what is the best path.
  - Types of Dynamic Routing Protocols: Link State, Distance Vector, Hybrid
- Distance Vector = take the least hop to transfer traffic thru router.
  - Example: RIP (Routing Internet Protocol), EIGRP (Enhanced Interior Gateway Routing Protocol)
- Link-State = take the fastest path to transfer traffic thru router even if it takes more hops.
  - Example: OSPF (Open Short Path First)
- Hybrid = Taking both Distance Vector and Link State advantage and combining them.
  - Example: BGP (Border Gateway Protocol)
- Static Routing = You set your own route for your router.
- Default Route = The last resort for routing if the router can't route to its destination.
- Administrative distance = used by router to determine which routing protocol have more priorty
- Time to Live = to prevent routing to be stuck on a routing loop.
- Traffic shaping = set bandwidth to the applications that needs high priorities
- Quality of Service = The service you are using to prioritize the rule list and can be configured inside a router, switches, firewalls, QoS device.
