# Domain 1.3

## Copper

- Copper Cabling = Foundation of Ethernet networks.

#

### Twisted Pair Copper Cabling

- Inside of a Twisted pair
  - 4 pairs of wires. Pairs are twisted around each other.
  - Sending equal and opposite signals down both side of the wires.
  - Signals = Transmit+, Transmit- or Receive+, Receive-

- The Twist of the wire is the secret.
  - Keeps a single wire constantly moving away from interference.
  - Allow us:
    - To compare those signals on the other end.
    - Reconstruct what may have been damaged/ interfered with during transmission.
   
- The different pairs have different twist rates
  - Another way we could use to reconstruct that signal on the other side.

- Copper Cable Categories

<img width="435" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/453fab46-521f-47df-9f5d-45b442ad86ed">

#

### Coxial Cables

- Two or more forms share a common axis.
- RG-6 used in televsion/ digital cable.
  - High speed internet over cable.

#
 
### Twinaxial Cable

- Two inner conductors; Twins
- Common on: 10 GB Ethernet SFP+ cables,
  - Full duplex, Five metere, low cost, low latency compared to twisted pair.
 
#

### Termination Standards

- Standard dictate exactly how you should install and use twisted pairs and copper cable connections.
- Telecommunications Industry Association (TIA)
  - Standard in North America
- TIA/EIA 568: Commerical Building Telecommunication Cabling Standard.
- Pin and Pair assignments of 8 conductor 100 ohm balanced twisted pair cabling.
- Should follow only one set of cabling.
  - T568A and T568B, determines what type of colors of cables we will use when punching down ethernet connections.
  - T568A: Horizontal Cabling
  - T568B: Traditional to many organizations to use.
 
#

Color of T568A: 
- White and Green
- Green
- White and Orange
- Blue
- White and Blue
- Orange
- White and and Brown
- Brown

Color of T568B:
- White and Orange
- Orange
- White and Green
- Blue
- White and Blue
- Green
- White and and Brown
- Brown

<img width="759" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/011c9b74-d3ee-4502-98fd-e95d3f265167">

#

## Optical Fiber

- If you are physically connected to network but not using Copper. Then you probably using Fiber optics.
  - Network Communication using light instead of electical signals.
- No Radio Frequences signals.
  - Difficult to monitor or tap.
- Signal slow to degrade and can transmission long distances.
- Immune to radio interference.

### Multimode Fiber

- Short-range communication
- Up to 2 km
- Inexpensive light source; LED light.
- Multimode: the core of the fiber itself is larger than the wavelength of light being sent thru it.
  - Different code as they pass thru the fiber.

<img width="593" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/9ca97454-ecbc-42b6-9232-bc0a2290c018">

### Single-mode Fiber

- Long-range communication
- Up to 100 km without processing
- Expensive light source; Laser beams

<img width="548" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/68728a72-8c2a-4306-9185-b4f00ce739b9">

#

## Connector Types

### Local Connector (LC) - Fiber

- Have 2 different fibers inside, Usually send and reciever.
- Have locks that you have to push down.
- Small, so it's on the most recent routers and switches.

<img width="371" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/d8aec08d-33d6-4c3c-ab91-6af07b7e2046">

#

### Straight Tip (ST) - Fiber

- Slightly larger than LC.
- Old, slightly twist them to lock in place.

<img width="354" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/f908fecb-518d-47a4-99dd-e0830bcb06d0">

#

### Subscriber Connector (SC) - Fiber

- Square connectors

<img width="304" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/b7201ec3-3377-4028-a01c-06fc3d3df21b">

#

### Mechanical Transfer Registered Jack (MT-RJ) - Fiber

- Very small connector.
- 2 tiny fiber connectors at the end.
- Good for small available space.
- Similar to LC connector, locking mechanism on top.

<img width="393" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/d98c26c9-577a-4f33-b241-0c07ab195193">


#

### UPC and APC - Fiber

- Fiber connection = light; laws of physics apply
- Return loss: Light reflected back to the source, creating inefficiency from sending light to the other end.
- We can use UPC or APC to minimize the return loss.

UPC = (Ultra Physical Contact)
- Polished at a zero degree angle.
- High return loss

<img width="294" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/36018e2a-24dd-4e8e-b63e-44dce5e91b27">

APC = (Angle Physical Contact)
- Polished at an eight degree angle.
- Lower Return loss, generally higher insertion loss than UPC.

<img width="307" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/c03adc43-8cb6-4c70-acb2-a6a01779f7e4">


#

### RJ11 Connector - Copper Connections

- Use: voice communication; Telephone & DSL Connection
- Registered Jack Type 11
  - 6 position, 2 conductor (6P2C)
  - RJ14 uses 6P4C for dual line use.

<img width="243" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/82e55798-1dd7-4ee4-9e2b-848b1b27ec34">

#

### RJ45 Connector - Copper Connetions

- Registered Jack Type 45
- Use: Ethernet Connection, Modular Connector
- 8 position, 8 conductor (8P8C)

<img width="272" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/f6e07e15-0839-4d2e-9f77-d1b3c9206d13">

#

### F-Connector

- Use: Cable Television; cable modem; DOCSIS (Data Over Cable Service Interface Specification)
- RG-6 type of coax cable, Commonly Threaded connector.

<img width="192" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/87f65bd8-8a19-411c-b314-8ec9568888f7">

#

### Transceivers/ Media Converters

Media Converters
- OSI Layer 1 device; physical layer signal conversion.
- Example: Convert a fiber connection to a copper connection; vice versa.
- Extend a copper wire over a long distance; convert it to fiber and back again.
- You only have fiber connection but the switch only has copper ports. Can convert temporary to fiber.

Transceivers
- Transmitter and receiver; usually in a single component.
- Provides a modular interface; add the transceiver that matches your network.
- Adding a thing that you can switch type of converters.

<img width="439" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/5072cc50-7859-4e3c-9fe3-7651fbc127c7">

#

### Duplex Communication
- Two fibers; Transmit and recieve.

<img width="715" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/d397a381-5e3d-4404-a46c-d816bb9744ce">


### Bi-Directional (BiDi) Transceivers
- Traffic in both directions with a single fiber; use two different wavelengths.
  - You can transfer and receive traffic over a single strand of fiber.
- Reduce number of fiber runs by half.

<img width="695" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/d11340de-cad7-44cb-a39c-6b5049a4b8bf">


#

### SFP and SFP+

Small Form-factor Pluggable (SFP)
- Commonly used to provide 1 Gbits/s fiber
- 1 Gbit/s RJ46 SFPs also available.

Enhanaced Small Form-factors Pluggable (SFP+)
- Exactly the same phyysical size as SFPs.
- Support: up to 16Gbit/s
- Common use with 10 Gigabit Ethernet.

#

### QSFP and QSFP+

Quad Small Form-factor Pluggable
- 4 Channel SFP = Four 1 Gbit/s = 4 Gbit/s

Enhanced Quad Small Form-factor Pluggable
- QSFP+ = four channel SFP+, Four 10 Gbit/s = 40 Gbit/s

Efficiency: 
- Combine four SFPs into a  single transceiver
  - Cost Savings in fiber and equipment.
- Use bi-directional QSFPs/QSFP+
  - Additional efficiency over a single fiber.
 
<img width="181" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/101305b3-1dfc-4ed2-b469-409ed8120769">

#

## Cable Management

### Patch Panel/ Patch Bay

- Direct cable connection, usually under the floor or over the ceiling back to a closet for a large office desk computers.
  - Inside the closet, usually a Patch Panel.
  - Wire from the desks are usually punch down into that patch panel.
  - The other side of the patch panel usually have a RJ45 connectors that allow the desks computer to switches.
- Once punched into the patch panel from the desk, you usually only configurate the other side of the connection/ the RJ45 side.

<img width="777" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/f1608402-0e0d-4017-ab62-9bdfc66ab4ad">

Copper Patch Panel
- Patch panel can have punch-down block on one side and RJ45 connector on the other side.
- Patch panel can also have punch-down connections on both sides.
  - Allows to make moves, adds, and changes to the network by plugging in the front of those patch panels. Rather than changing any of the wires that go back to the desk.


#

### Fiber Distribution Panel

- Don't usually run fiber from someone's desk on a large office.
  - Expensive by installation.
- Common run fiber between floors of a building or between separate buildings.
- Both sides of the fiber connection, often install a fiber distribution panel.
  - Generally run more than one fiber connection at a time using the fiber distribution panel because we are already going thru the cost and expense of running fiber.
- Design: Fiber bend radius
  - Bending loops on the inside because there is a maximum bend radius associated with fiber optics.
  - Often includes extra loops for extra service.
    - Extra fiber for future changes for extension if needed. Inexpensive insurance.
   
<img width="444" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/103fdc17-3288-4f77-bc16-77d58c61c6bb">

#

### Punchdown block type - 66 Blocks

- Early type of common blocks
- Usually used for analog voice communication; Telephones
  - Some digital links
- Connect one side of the connection on the left side and the other side of the connection on the right in order to extend.
- Wire and punch down tool, No additional connector required.
  - Wire-to-wire patch panel.
- Replaced by 110 blocks.

<img width="344" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/3796d9da-3c53-4aac-bd2c-50ba639fa4cf">

#

### Punchdown block type - 110 Blocks

- Usually for digital/ high speed ethernet connections.
- Wire-to-wire patch panel.
- Patch Cat5 and Cat6 cables.
- Wires are punched into the block; connecting block is on top.
- Additional wires punched into connecting block, patch the top to the bottom.

<img width="365" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/490e9dbf-039e-47c7-b8ef-4a3992b08436">

#

### Punchdown block type - Krone Block

- An alternative to the 110 block.
  - Common in Europe
- Used for: Analog and digital communication, different model can support higher frequencies.

<img width="331" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/f365a166-e976-43b1-8576-f842e8f3120e">

#

### BIX 

Building Industry Cross-Connect)

- Created in 1970s by Nothern Telecom.
- Modern BIX = GigaBIX performance is better than Cat6 cable standard. 
  - Support Cat6 and better connection allowing to run fast ethernet over a BIX block.
 
<img width="730" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/0488b229-11b7-4666-a0d3-54263cd724de">

#

## Ethernet Standards

