 # What are Packets and Frames

Packets and frames are like smaller parts that come together to make a bigger message. But in the OSI model, they have specific roles. A frame is like an envelope within an envelope - it's at layer 2, so it doesn't have things like IP addresses. It's as if you send an envelope (packet), but inside it, there's another envelope (frame) that holds the actual information.

Piece of Data with IP Address information = Packets

Piece of Data without IP Address information = Frames

<p align="center">
<br/>
<img src="https://i.imgur.com/Oi0mMnC.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

Questions 1: What is the name for a piece of data when it does have IP addressing information?

Answer: `Packets`

Questions 2: What is the name for a piece of data when it does not have IP addressing information?

Answer: `Frames`

<h2></h2>

# TCP/IP (The Three-Way Handshake)

Transmission Control Protocol

TCP/IP protocol consists of four layers and is arguably just a summarised version of the OSI model. These layers are:

- Application
- Transport
- Internet
- Network Interface

<h2></h2>

- TCP model adds information at each layer as data moves through, similar to OSI model.

- This process is called encapsulation, with decapsulation being the reverse.

- TCP is connection-based; it sets up a connection between a client and server before sending data.

- TCP ensures data is received on the other end, using a process called the Three-way handshake.

<p align="center">
<br/>
<img src="https://i.imgur.com/Y47HtbR.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

<h3>TCP Packet Header</h3>

TCP packets contain various sections of information known as headers that are added from encapsulation. Let's explain some of the crucial headers in the table below:

- Source Port: Port number used by the sender to send data, chosen randomly from available ports.
- Destination Port: Port number where the receiving application or service is running (e.g., webserver on port 80), not random.
- Source IP: The sender's device IP address.
- Destination IP: The recipient device's IP address.
- Sequence Number: The first data piece gets a random number for tracking when connection occurs.
- Acknowledgement Number: The next data piece's number is the previous one plus 1.
- Checksum: A math check for data accuracy; it's like a data `integrity` stamp. This value is what gives `TCP integrity`.
- Data: Where the actual file bytes being sent are stored.
- Flag: This header controls how devices handle the data transfer, with different flags leading to different behaviors during the handshake process.

<p align="center">
<br/>
<img src="https://i.imgur.com/LEyBlLE.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

<h3>Three-way handshake </h3>

The term given for the process used to establish a connection between two devices. The Three-way handshake communicates using a few special messages.

- SYN: The first message sent by a client to start a connection.
- SYN/ACK: Server's response to confirm the connection initiation.
- ACK: A message to acknowledge successful data receipt, sent by either side.
- DATA: The actual data, like a file's bytes, sent after the connection is established.
- FIN: A message to properly end the connection when it's done.
- RST: A last-resort message that abruptly ends communication due to a problem like service issues or system faults.

The diagram below shows a normal Three-way handshake process between Alice and Bob. In real life, this would be between two devices.

<p align="center">
<br/>
<img src="https://i.imgur.com/esf02WW.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

- Data is given a random number sequence and reconstructed using it.

- Both computers must agree on the same number sequence for the data to be in the right order.

- Three steps are used to agree on this order:
  - (SYN) - Client says, "Let's sync with my Initial Sequence Number (ISN) at 0"
  - (SYN/ACK) - Server responds, "Let's sync with my ISN at 5,000, and I acknowledge your ISN at 0"
  - (ACK) - Client acknowledges the server's ISN at 5,000 and sends data at its ISN+1 (0 + 1)
 
<h2></h2>

<h3>TCP Closing a Connection:</h3>

- TCP closes a connection when it's sure the other device got all the data.

- Closing connections promptly is a good idea because TCP uses system resources.

- To start closing, one device sends a "FIN" packet to the other, and the other acknowledges it.

<p align="center">
<br/>
<img src="https://i.imgur.com/McohiIt.png" height="90%" width="90%" alt=""/>
<br />
In the illustration, we can see that Alice has sent Bob a "FIN" packet. Because Bob received this, he will let Alice know that he received it and that he also wants to close the connection (using FIN). Alice has heard Bob loud and clear and will let Bob know that she acknowledges this.

<h2></h2>

Questions 1: What is the header in a TCP packet that ensures the integrity of data?

Answer: `Checksum`

Questions 2: Provide the order of a normal Three-way handshake (with each step separated by a comma)

Answer: `SYN,SYN/ACK,ACK`


<h2></h2>

# UDP/IP

User Datagram Protocol

- UDP = a stateless protocol, doesn't need a constant connection between devices to send data.

- There's no Three-way handshake or synchronization between devices.

- UDP is used when losing some data is okay (like in video streaming or voice chat) or when a shaky connection won't break everything.

- With UDP, there's no fancy setup for connecting two devices. It doesn't worry about whether data gets there safely like TCP does.

- UDP packets are basic and have fewer headers than TCP packets.But they both use some standard headers.

<h2></h2>

<h3>UDP Header</h3>

- Time to Live (TTL): This is like an expiration timer for the packet, so it doesn't hang around forever in the network.
- Source Address: It's the sender's IP address, so data knows where to go back if needed.
- Destination Address: It's the receiver's IP address, so data knows where to head next.
- Source Port: This is like the sender's departure gate at the airport. It's randomly picked from available gates.
- Destination Port: This is like the arrival gate for data on the receiver's side, for example, a web server's gate.
- Data: It's where the actual information, like a file's bytes, is stored for transmission.

<h2></h2>

- Recall that UDP is stateless. No acknowledgement is sent during a connection.

- The diagram below shows a normal UDP connection between Alice and Bob. In real life, this would be between two devices.

<p align="center">
<br/>
<img src="https://i.imgur.com/RwpYa7G.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

Questions 1: What does the term "UDP" stand for?

Answer: `User Datagram Protocol`

Questions 2: What type of connection is "UDP"?

Answer: `Stateless`

Questions 3: What protocol would you use to transfer a file?

Answer: `TCP`

Questions 4: What protocol would you use to have a video call?

Answer: `UDP`


<h2></h2>

# Ports 101 (Practical)

- Ports are like docking points for data exchange.

- Imagine a harbor with different docks for various types of ships.

- Ships have to find a matching port based on their size and needs.

- Once they align, they connect to that specific port.

- Just like a cruise liner can't use a small fishing vessel's port, different data needs the right port to connect.

<h2></h2>

- Ports dictate where and what can park.
- They are used by networking devices for strict communication rules.
- Once a connection is made, all data goes through these ports.
- Ports are numbers from 0 to 65535.

<h2></h2>

- Ports range from 0 to 65535.
- It's easy to lose track of which application uses which port.
- We use standard rules to associate applications with ports.
- For example, web browser data goes over port 80.
- This helps different web browsers understand data in the same way.
- Any port that is within 0 and 1024 (1,024) is known as a common port. Let's explore some of these other protocols below:

<p align="center">
<br/>
<img src="https://i.imgur.com/PHsd4RU.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

- Protocols strictly adhere to standards.
- You can use non-standard ports for applications.
- Applications expect the standard port, so use a colon (:) with the port number.





