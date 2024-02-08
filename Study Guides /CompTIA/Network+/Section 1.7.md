# Network Architectures

## Three tier Architecture

Core 

- The center of the network
- Web servers, databases, applications
- Many people need access to this

Distribution

- A midpoint between core and users
- Communication between switches
- Manage th path to the end users

Access 

- Where the users connect
- End stations, printers

Diagram of Three tier architecture

![image](https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/15e35b34-e64f-44c7-8bda-5bd3d1b59af8)

#

## SDN (Software Defined Networking)

Networking devices have different functional planes of operation:

- Data plane, control plane, and management planes.

Splits the functions into separate logical units:

- Extend the functionality and management of single device.
- Perfectly built for the cloud.

#

### Infrastructure layer / Data plane

- If a switch then: Process the network frame and packets
- If firewall then: Forwarding, trunking, encrypting, NAT (Network Address Translation)

#

### Control Layer / Control plane

- Manages the action of the data plane
- Routing tables, session table, NAT Tables
- Dynamic Routing protocol updates

#

### Application layer / Management plane

- Configure and manage the device.

#

## Spine and Leaf Architecture

- Each leaf switch connects to each spine switch and Each spine switch connects to each leaf switch

- Each leaf switches do not connect to each other, same for the spine switches

Top of rack switching

- Each leaf is on the top of a physical network rack
- May include a group of physical racks

Advantages:
- Simple cabling, Redundant, Fast

Disadvantages:
- Additional switches may be costly since adding another server will need another leaf and will need to connect to all the spines.

![image](https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/ccee8c59-794a-4bee-83ef-b8409cb47240)

#

### Traffic Flows

Traffic flows within a data center
- Important to know where traffic starts and ends

East-west traffic:
- Traffic between device in the same data center
- Relatively fast response times.
- For example: Image server and web server traffics

North-south traffic:
- Ingress/Egress to an outside device
- A different security posture than east-west traffic
- Traffic going outside of the data center.

![image](https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/e00f42c2-f7ea-4a89-886c-8b8b1b24558c)

#

## Network Locations (Branch office vs On-Premises Datacenter vs Colocation)

Branch office:

- A remote location
- Client devicesm printersm switch/router/firewall

On-Premises Data Center:

- Technology is located in house
- Requires power, cooling, and ongoing monitoring

Colocation:

- Share a data center with others, multiple company have their data in one data center, separate by cages.
- local oversight and monitoring

#

## Storage Area Networks (SAN)

- Looks and feels like a local storage device
- Block level access
- Very efficient reading and writing

Requires a lot of bandwidth
- May use an isolated network and high speed network technologies
- have to access this SAN across the network

#

### Fibre Channel (FC)

Specialized high speed topology

- Connect servers to storage
- 2-, 4-, 8- and 16 GB per sec rates
- supported over both fiber and copper

Servers and storage connect to fibre channel switch:
- Server (initiator) needs a FC interface
- Storage (target) is commonly referenced by SCSI, SAS, SATA commands.

#

### Fibre Channel ove Ethernet (FCoE)

User Fibre Channel over an Ethernet network
- No special network hardware needed
- USually intergrates with an existing Fibre Channel infrastructure
- Not routable.

#

### ISCSI

Internet Small Computer System Interface

- Send SCSI Command over an IP network
- Created by IBM and Cisco and now RFC standard.

Makes a remote disk look and operate like a local disk
- Like Fibre Channel

Can be managed quite well in software
- Drivers availalbe for many OS
- No propritary topologies or hardware needed.
