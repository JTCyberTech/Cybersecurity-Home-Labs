# MAC Address

Hub = Repeater
- Take signal from ports and recreate multiple copies of it and send it out to all connected cables.

MAC Address = Phyiscal Address
- Unique identifier for the network card.
- Hexadecimal vaule, 48 bit address. Each Hexadecimal = 4 binary characters.
- First 6 digits = Original Equipment Manufacturer (OEM)
- Last 6 digits = Organizationally Unique Identifier (OUI)

Cyclic Redundancy Check (CRC)
- Used to verify that the data is good.
- If bad data, knows to resend it.

#

# Ethernet Frames

- Preamble: Job = know when a frame is coming.
- Destination MAC: Address to know where it's going.
- Source MAC: Return Address to know where the reciever send it back.
- DATA Type: Also "Ether Type" job = what kind of data is hauling. (0800 or ARP)
- DATA: Can haul Min: 64 bytes or octets. Max: 1522 bytes or octets.
  - PAD: Pushes the data to absolute minimum size 
- FCS: Frame Check Sequence = 32 bits cyclic redundancy check, check the value if it's not correct, resend.
  - Used for error detection.



