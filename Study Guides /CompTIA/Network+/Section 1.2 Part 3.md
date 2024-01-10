# WAN Termination

## Demaraction Point (demarc)

- Physical location that designates the connection point between the service from WAN Provider or ISP to your internal network.
- The point where you connect with the outside world.
- Used everywhere:
  - Home: the Verizon Box outside house.
- Location of the Demarc is important.
  - Can understand if problem occur, if it's provider side of the demarc or your side of the demarc.
  - If your side: CPE or Customer Premises Equipment.
    - You can connect to your network to do troubleshooting.

#
   
## Smartjack

- Network Interface Unit (NIU)
  - Device that determines the demarc
  - Network Interface Device, Telephone Network Interface
  - Owned by the Network provider, so the network provider can test remotely.
 
- Smartjack
  - More than just a simple interface
  - Can be a circuit card in a chassis.

#

# Virtual Networks

- Physical Server farm with 100 individual computers.
  - All servers are connected with multiple VLANs, redundant connections, high speed communications.
- With Virtual Network, we can migrate the 100 physical servers.
  - We can create 100 virtual servers within 1 single physical device.


#
 
## Network Function Virtualization (NFV)

- Replace physical network devices with virtual versions.
  - Moving and Manage it from the hypervisor.
- Same functionality as a physical device
  - Routing, Switching, load balancing, firewall are all within the virtual system.
- Provide with additional capabilities.
  - Example: when you need a new switch or router, don't need to go out to buy it. Simply click and deploy from hypervisor.
- Can have many different deployment options:
  - Add virtual machines, container, fault tolerance.
 
#

## The Hypervisor

- Virutal Machine Manager or VMM.
  - Responsible for managing all guest OS, all virtual systems, virtual network connections deployed on the virtual system.
  - Hardware responsibilities: CPU, Networking, Security.
 
#

## vSwitch

- Virutal Switch: Move the physical switch into the vitual environment.
- Functionality is similar to physical switch.
  - Forwarding options, link aggregation, port mirroring, NetFlow.
- Deploy by drag and drop or click, automate witih orchestration.

#

## vNIC

- Virtual Network Interface Card.
- Inside the Virtual Machine, need a vNIC to communicate with the rest of the network.
- Configured and connected thru Hypervisor.
  - enable additional features
  - VLAN, aggregation, multiple interfaces.
    - Might need multi network interface card for load balancing.
