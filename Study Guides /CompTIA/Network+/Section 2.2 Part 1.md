# Network Topologies

Messer
- Useful in planning new network
- Assists in understanding signal flow to troubleshoot problems.

Meyers
- Network Toplogies = how network is laid out.
- 2 types of topology structures
  - Physical: how the ocmputers are actually laid out in a room.
  - Logical: how data is sent between them.

Dion
- Physical topology = physical layout of the cabling.
- Logical topology = network flow.


#

## Star Topology

Messer
- Hub and spoke
- Used in most large and small networks.
- All devices are connected to a central device.
- Example: Switch Ethernet networks; The switch is in the middle.

Meyers
- Have multiple hosts that will connet to some centralized box.
- Box can be a hub or a switch.
- Can also be called hub-and-spoke.

Dion
- Most popilar physical LAN topology where device connect to single central point.
  - Central point can be switch.
- Problem: only have one central device, if the central device fails = entire network fails.
- Single point of failure.
- Common and inexpensive.

Hub-and-Spoke Topology
- Similar to Star but with WAN links instead of LAN connections and it is used for connecting multiple sites.
- Still have a single point of failure. If central point failure, the network will fail.

#

## Ring Topology

Messer
- Used in many popular topologies for wide area networks.
- Don't often see token ring topologies in local area networks.
- Still used in Metro Area Networks (MANs) and Wide Area Newtworks(WANs).
- Since it goes around in circle, if there is a faulty, it will loop back to go to the other side.

Meyers
- Frames will travel around the ring.
- Problem: if there's a break in the cable between the host and the subsequent host.

Dion
- Uses a cable running in a circular loop where each device connects to the ring but data travels in a singular direction.
- Have to wait their turn to communicate or will have a collision.
- Token Ring = Ring topology that uses an electronic token to prevent collisions when communicating on the network.
- Still vulnerable to being broken, cut the cable that would take down the network; no redundancy.
- FDDI ring = two rings one on top of the other, one operates in clockwise direction; other counterclockwise.
  - Gets redundancy because if one broke, other can take over.
- **Exam: ring = FDDI and redundancy** beacuse modern ring is all FDDI.


#

## Bus Topology

Messer 
- Early types of ethernet network were not switched ethernet.
- Run over Coaxial cable.
- Single Cable running thru the walls or down the center of the room.
- Problem: One break in the link disables the entire network.
- Modern Automobile uses Controller Area Network (CAN bus)
  - Used to connect all of the different sensors/ controllers inside of the automobiles to make the care safer.

Meyers
- Oldest, all the hosts are connected to a single trunk cable.
- Disadvantage = if cable breaks, all of the hosts on the cable go down.
- All the host shares the same bandwidth. If you add host to the cable, it gets slower.

Dion
- Uses a single cable where each device taps into by using either a vampire tap or a T-connector.
- Forms a single collision domain; if all the device trying to talk at the same time, you will have a collision because they are all sharing the same cable.
  - Have to take turns to communication.
 
#

## Mesh Topology

Messer
- Multiple links to the same place
- Can be fully connected or partially connected.
- It's Redundancy, fault-tolerance, load balancing.
- Common used in Wide Area Networks (WANs)
  - Can create multiple links to other sites, so you can have a primary connection from one site to the other and then a backup/secondary connection if there is a problem.

Meyers
- Looks like a Ring topology but every single host is connected to all other hosts.
- Creates fault tolerance, meaning if there's a break in any cable, it does not affect anyone else.
  - Just affects the break between on host to another.

Dion
- Full-Mesh Topology: Optimal routing is always available as every node connects to every othe nodes.
  - Every expensive and too complicated, x = n(n-1)/2 for number of connections.
  - Usally see full-mesh in logical methods.
- Partial-Mesh Topology: Hybrid of the full-mesh and the hub and spoke topologies.
  - Might see in real world.
  - Can provide optimal routes between some sites but not all sites.
    - Target the busiest sites by doing surveys.

#

## Hybrid Topology

Messer 
- Combination of one or more physical topologies.
- Can have 3 star topologies structure that is connected with a ring topology.

Meyers
- Star-bus topolgy

#

## Wireless Topologies 

Messer
- Infrastructure:
  - All devices communicate thru Access Point.
  - The most common way to use wireless connections.
- Ad Hoc Networking:
  - Only have two devices and there is no access point.
  - Connect one device to another using Ad Hoc.
  - Devices communication amongst themselves.
- Mash:
  - IoT devices
  - Ad Hoc Devices work together to form a mesh cloud.
  - Can self heal, if you turn off one IoT devices, the remaining devices will self heal and redesign themselves into a mesh network that will allow them to continue the communication.
