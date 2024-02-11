# Network Devices

## Hub

Multi port repeater
- Traffic going in one port and repeat it to every other port.
- OSI Layer 1.

Everything connected to hub is operating at half duplex.
- You can either send or receive information from the hub, cant do both at the same time.

Becomes less efficient as network traffic increases.

10 MB/s or 100 MB/s


#

## Bridge

Imagine a Switch with two to four ports
- Makes forwarding decision in software.

Connect Different physical networks
- Can connect different topologies
- Gets around physical network size limitation/  collisions.

OSI Layer 2 device
- Distributes traffic based on MAC address

An example of a modern bridge is a wireless access point
- Bridges wired Ethernet to wireless.

#

## Switch

Bridging done in hardware
- Application specific integrated circuit (ASIC)

OSI Layer 2 Device
- Forwards traffic based on data link address

Many ports and features
- Core of enterprise network
- May provide power ove Ethernet (PoE)

Multilayer Switch
- Layer 3 (routing) functionality

#

## Router

Routes traffic between IP Subnets

- OSI Layer 3 device
- Routers inside switches sometimes called layer 3 switches
- Layer 2 = Switch, Layer 3 = Router

Often connect diverse network types:
- LAN, WAN, copper, fiber

#

## Access Point

Not a wireless router
- A wireless router is a router and an access point in a single device

An access point is a bridge 
- Extends the wired network onto the wireless network
- OSI Layer 2 device.

#

## Cable Modem

Broadband
- Transmission across multiple frequencies
- Different taffic types.

Data on the cable network = DOCSIS (Data Over Cable Service Interface Specification)
- Supports a wide range of speeds
- 4 Mbits/s thru 250 Mbits/s
- Gigabit speeds are possible

Can support Multiple services
- Data, Voice, video.

#

## DSL Modem

ADSL (Asymmetric Digital Subscriber Line)
- Uses telephone lines.

Download speed is faster than upload speed (Asymmetrical)
- Based on how far away you are from Central Office (CO)

#

## Repeater

Recieve Signal, Regenerate, Resend
- No fowarding decision to make.

Commonly use to:
- Boost copper or fiber connections
- Convert one network media to another
- Extend wireless network reach.

#

## Media Converter

OSI Layer 1
- Physical Layer Singal conversion

Extend a copprt wire over a long distance
- Convery it to fiber and back again

You have fiber
- Switch only as copper ports

Almost always powered especially Fiber to copper.

#

## Wireless LAN Controllers

Centralized management of access points
- Single pane of glass: a single management screen, can make configuration changes and manage our entire access point infrastructure from one central management station.

Can deploy new access point with Wireless LAN Controller by sending out the configuration to that device.
- Performance and security monitoring
- Configure and deploy changes to all sites
- Create report on how many access points are in use or how many users may be connected.

#

## Load Balance

Distribute the load
- Multiple servers, invisible to the end user

Allow for large scale implementations
- Web server farms, database farms.

Fault tolerance
- Server outages have no effect
- Very fast convergence

![image](https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/3140302b-d80c-4a5d-91a6-e859cbf15e69)

#

## IDS / IPS

Intrusion Detection System / Intrusion Prevention System
- Watch network traffic

Intrusions
- Explots against operating systems, applications, etc.
- Buffer overflows, cross-site scripting, other vulnerabilities

IDS 
- Alerts if it find an attack

IPS
- Able to stop that tarffic before getting into your internal network

#

## Proxy Server

Sits between the users and the external network
- Sits at one part of the network and another to be able to allow or disallow certain traffic type to travel across the network.

Handles end user's communication: Receives the user requests and sens the request on their behalf (the proxy)
- A user wants to communicate to a web server > Request is made to the proxy > proxy communicates to the web server > Proxy recieve response to that website server > Examines response to make sure that everything within that response is safe > send response down to the originating station.

Userful for: 
- Caching information, access control, URL filtering, content scanning

Applications may need to know how to use the explicit proxy
- Application used to communicate thru proxy has to be configured with the details of this proxy configuration.

Some proxies are invisible to end users (transparent) proxy
- Don't need any special application or configurations on the end use workstation.

### Application Proxies

Most proxies in use are application proxies
- The proxy understands the way the application works.

A proxy may only know one application: 
- HTTP or HTTPS = Web proxy

Many proxies are mutlipurpose proxies
- HTTP, HTTPS, FTP, etc

#

## VPN Headend/ VPN Concentrator

Virtual Private Network
- Encrypted (private) data traversing a public network

Concentrator / Head-end: purpose built to provide encryption and decryption capability, usually is able to do it very fast in the hardware of the concentrator.
- Encryption/ Decryption access device
- Often integrated into a firewall

Many deployment options
- Specialized cryptographic hardware
- Software based options available.

#

## VoIP Techologies

PBX (Private Branch Exchange)
- Phone Switch
- Connects all phones in office to single PBX and the PBX connects to phone provider network
- Analog telephone lines to each desk.

VoIP PBX
- Integrate VoIP Devices with corporate phone switch
- Allows connect all VoIP Phones to each other within our organization and can also combine this with a voice gateway that would convery between VoIP to the traditional phone line.

Voice Gateway
- Converts between VoIP protocol and traditional PSTN (Public Switch Telephone) protocols.
- Often built-in to the VoIP PBX, Can easily jump between VoIP and traditional analog telephone network.

#

## Network-based firewall

Filter traffic by port number/ IP Address or application
- Traditional: filter traffic by port/ IP Address. NGFW: filters also with application

Many Firewalls also have Encryption traffic
- VPN concentrator functionality built in , so encrypt traffic to end users or between different sites.

Most firewalls can be layer 3 devices (routers)
- Often sits on the ingress/egress of the network
- Network Address Translation (NAT)
- Dynamic routing

#

## Printer

Color/ B and W output
- Paper Documents
- Photos

All in one or AIO device
- Printer, scanner, copier, fax

Connectivity
- Ethernet, 802.11 Wireless, USB, Bluetooth / infrared

#

## Phyiscal ACcess Control Devices 

Card Reader
- Access with a smart card

Biometric Authentication
- Fingerprint, retina, voiceprint
- Usually stores a mthemtical representation of your biometric
  - Actual fingerprint isn't usually saved
 
Ethernet connected
- IP Address Configured static or DHCP

#

## Cameras

CCTV (Close Circuit Television)
- Replace physical Guards

Camera features are important
- Motion recognition can alarm and alert when something moves
- OBject detection can identify a license plate or person's face

Often many different camers
- NEtworked together and recorded over time.

#

## HVAC

Heating Ventilation Air Conditioning
- Thermodynamics, Fluid mechanics, Heat Transfer

A complex Science
- Not something you can properly design yourself
- Must be integrated into the fire system

PC manages equipment
- Makes colling and heating decisions for workspaces and data centers
- Network Connectivity is critical

#

## IoT (Internet of Things) Devices

Application
- Refrigerators

Smart Devices
- Smart Speakers respond to voice commands

Air Control
- Thermostats, Temperature control

Access:
- Smart Doorbells

May require a segmented network
- Limit any security breaches

#

## SCADA /ICS

Supervisory Control and Data Acquistition System
- Large scale, multi site Industrial Control System (ICS)

Central PC Managing all equipment thru a centralized network connection:
- Power generation, refining, manufacturing equipment
- Facilities, industrial, energy, logistics.

Distributed Control Systems
- Real-time Information
- System Control

Requires Extensive Segmentation
- No access from the outside
