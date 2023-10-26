# What is the OSI Model?

The `OSI model (Open Systems Interconnection Model)` is the `fundamental` model used in networking. This critical model provides a `framework` dictating how all networked devices will send, receive and interpret data.

A big `advantage` of the `OSI model` is that it `allows different devices on a network` to `talk to each other`, `even` if they look and `work differently`. If data follows the OSI model's `rules`, all devices can `understand` it.

The OSI model consists of `seven layers`, is like a seven-story building. Each floor, from the top (Floor 7) to the bottom (Floor 1), has its own job to do and a specific role in making communication work.

At every individual layer that data travels through, specific processes take place, and pieces of information are added to this data. this process is called `encapsulation`.

<p align="center">
<br/>
<img src="https://i.imgur.com/74wLHFn.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

Questions 1: What does the "OSI" in "OSI Model" stand for?

Answer: `Open System Interconnection`

Questions 2: How many layers (in digits) does the OSI model have?

Answer: `7`

Questions 3: What is the key term for when pieces of information get added to data? 

Answer: `Encapsulation`

<h2></h2>

# Layer 7 - Application

The `application layer` of the OSI model is the layer that you will be `most familiar` with because the application layer is the layer in which `protocols and rules` are in place to `determine how` the `user should interact with data sent or received`.

`Common apps` like email, web browsers, and file-sharing programs (like FileZilla) have user-friendly, Graphical User Interface (GUI), screens for `handling the stuff you send or get`. There's also stuff like `DNS` (Domain Name System) that turns website names into their actual numbers.


<h2></h2>

Questions 1: What is the name of this Layer?

Answer: `Application`

Questions 2: What is the technical term that is given to the name of the software that users interact with?

Answer: `Graphical User Interface`

<h2></h2>

# Layer 6 - Presentation

The layer in which `standardisation` starts to take place. Because software developers can develop any software such as an email client differently, the data still needs to be handled in the same way — no matter how the software works.

This layer `acts as a translator` for `data to and from` the application layer `(layer 7)`.

The `receiving computer` will also `understand data` sent to a computer in `one format` destined for in `another format`.

For Example: you sent an email, the other user had another email client to you, but the `contents of the email will still need to display the same`.

- Security features such as `data encryption` (like `HTTPS` when visiting a secure site) occur at this layer.

<h2></h2>

Questions 1: What is the name of this Layer?

Answer: `Presentation`

Questions 2: What is the main purpose that this Layer acts as?

Answer: `Translator`

<h2></h2>

# Layer 5 - Session

Once `data` has been `correctly translated or formatted` from the `presentation layer` (layer 6). 

- `Session layer` (layer 5) will `begin to create a connection` to the `other computer` that the data is destined for.
- When a `connection is established`, a `session is created`.

The `session layer`, which is like a `traffic manager for two computers`, makes sure they're in `sync before sending and receiving data`.

- Once they're in `sync`, it `breaks the data into smaller chucks of data (packets)` and `sends them one by one`.
- `Helpful` because if the `connection gets interrupted`, it only needs to `resend the missing parts`.
- Example: Reloading a saved game from where you left off, instead of starting all over.

Noting: `sessions are unique`, data cannot travel over different sessions, but in fact, only across each session instead.

- Example: Each chat session is unique, and the messages only travel within that specific chat, just like you're having separate conversations with different people on your messaging app.

<h2></h2>

Questions 1: What is the name of this Layer?

Answer: `Session`

Questions 2: What is the technical term for when a connection is successfully established?

Answer: `Session`

Questions 3: What is the technical term for "small chunks of data"?

Answer: `Packets`

<h2></h2>

# Layer 4 - Transport

Plays a `super important` part in `transmitting data across network`. When data is sent between devices, it follows `2 different protocol`s:

- TCP
- UDP

<h2></h2>

<h3>TCP</h3>

TCP (`Transmission Control Protocol`). 

- Designed with `reliability` and `guarantee`.

- This protocol keeps a steady connection between the two devices just `long enough` for them to `send and get` the data.

- TCP built `error checking` into its design. This "error checking" `guarantee` that data sent from the small chunks in the session layer (layer 5) has then been received and `reassembled in the same order`.

- 

- 
