# Data Communication

## Protocol Data Unit (PDU)

- Refers to "Transmission units"
- A different group of data at different OSI layers.
- Ethernet will send everything on a ethernet frame. MAC address to another MAC address.
  - Doesn't care what is inside.
  - Encapsulating all data in it and sending it across network.
- IP operates on a packet of data. (Layer 3)
  - Inside the IP packet = TCP or UDP.
  - IP doesn't care what is inside, simply knows that it's moving data across network from 1 IP address to another.
- TCP header or UDP headers
  - There will be TCP segment or UDP Datagram in that packet.

#

## Data encapsulation and Decapsulation

Layer 5,6,7 Application: Need to get data from the web server to the web client.
- Application Data exists at OSI Layers 5 6 and 7.

Layer 4 Transport: In order to send the application data, we need to transport it across the network using TCP.
- TCP Header will be place in front of the Application data and send it across.

Layer 3 Network: Need an IP Address to be able to send the TCP data and the application data.
- IP Header is place in front of the TCP Header, in order to send from an IP address to another.

Layer 2 Data Link: Over ethernet, Data Link Control is needed. Layer 2 Frame Header/ Frame Trailer: indicate the end of the frame.
- Layer 2 frame header encapsulates all of the information within.

Encapsulation: Source Device sending data to Destination Device
- Layer 5,6,7 = Add Application data.
- Layer 4 = Add TCP Header.
- Layer 3 = Add IP Header.
- Layer 2 = Add Frame Header and Frame Trailer.
- Layer 1 = Turn it to 1s and 0s and sending it to Destination Device.

Decapsulation: Destination Device recieving the data from Source Device.
- Layer 1 = Recieving the 1s and 0s from the Source Device.
- Layer 2 = Removing the Frame Header and Frame Trailer.
- Layer 3 = Removing the IP Header.
- Layer 4 = Removing the TCP Header.
- Layers 5,6,7 = Access the Application Data 

<img width="737" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/0062810d-0337-45cb-b2d6-c285939c811e">

#

## Dissecting a Frame

Starts in Layers 5-7 (HTTPS, SSH, IMAP)
Layer 4 (TCP, UDP)
Layer 3 (IP)
Layer 2 (MAC)

#

## TCP Flags

Inside the layer 4, we have TCP data.
- Within the TCP Header, there is TCP flag.
  - Helps to understand how we can process the data as going to network.
- The TCP flag controls the payload.
  - SYN - Synchronize sequence numbers
  - PSH - Push the data to the application without buffering
  - RST - Reset the connection
  - FIN - Last packet from the sender.
 
#

## Maximum Transmission Unit (MTU)

IP Header have Flags too.
- Most flags at IP header deals with fragmentation of data.
  - Too large to send, have to fragment the data to send smaller size.
 
The maximum size you are able to send by Maximum Transmission Unit (MTU)
- We don't want to fragment because it commonly slows doen overall flow of traffic.
- Losing a fragment, loses entire packet.
- Requires overhead along the path.

MTU sizes are usually configured once
- Based on the network infrastructure and don't change often.
A significant concern for tunneled traffic
- Tunnel may be smaller than your local thernet segment.
Can test by using the Ping command:
- Ping with DF and force a maximum size of 1472 bytes
  - 1500 bytes - 8 bytes ICMP Header - 20 bytes IP Address.
  - Windows: ping -f -l 1472 8.8.8.8
  - Linux: ping -D -s 1472 8.8.8.8
