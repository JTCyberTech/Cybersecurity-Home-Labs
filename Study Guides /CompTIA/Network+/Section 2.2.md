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



Key takeway:

- Dynamic Routing = Sending traffics from one router to another and deciding what is the best path.
  - Types of Dynamic Routing Protocols: Link State, Distance Vector, Hybrid
- Distance Vector = take the least hop to transfer traffic thru router.
  - Example: RIP (Routing Internet Protocol), EIGRP (Enhanced Interior Gateway Routing Protocol)
- Link-State = take the fastest path to transfer traffic thru router even if it takes more hops.
  - Example: OSPF (Open Short Path First)
- Hybrid = Taking both Distance Vector and Link State advantage and combining them.
  - Example: BGP (Border Gateway Protocol)
- 
