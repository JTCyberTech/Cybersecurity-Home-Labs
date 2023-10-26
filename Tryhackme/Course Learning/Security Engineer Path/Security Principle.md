# CIA

The Security Traid: confidentiality, integrity, and availability (CIA).

- Confidentiality: aim to ensure that only the intended persons or recipients can access the data.
  - Think of it like a secret diary. It means only the people you trust can read it, and nobody else should be able to sneak a peek.

- Integrity: aims to ensure that the data cannot be altered; moreover, we can detect any alteration if it occurs.
  - This is about making sure your diary isn't tampered with. If someone tries to change what you wrote, you should be able to tell that they did it.

- Availability: aims to ensure that the system or service is available when needed.
  - Imagine your diary is always there when you want to write in it. It's like having access to it whenever you need it, without it disappearing or being unavailable.

<h2></h2>

<h3>CIA in Case of Placing an Order for Online Shopping:</h3>

- Confidentiality: You expect that your credit card info stays a secret, known only to the payment processor. If you think someone shady might get your credit card number, you won't want to buy anything. And if there's a data breach, and your personal info gets out, the company will suffer big losses.

- Integrity: Let's say you fill in your order and an intruder messes with the shipping address. Your package goes to the wrong place. If the information isn't trustworthy, you won't want to shop there.

- Availability: To shop online, you need the store's website or app to work. If it's down or keeps giving you trouble, you'll probably give up and look for another store. Availability means the service needs to be up and running when you need it.

<h2></h2>

<h3>CIA as it relates to patient records and related systems:</h3>

- Confidentiality: Think of this like a secret vault for your medical records. Your healthcare provider has to keep your medical information private and can get into legal trouble if they spill the beans. It's like a locked diary that only you and your doctor should read.

- Integrity: Imagine your medical record is like a puzzle, and each piece represents a part of your health history. If someone messes with those puzzle pieces, either by accident or on purpose, it's like putting the wrong pieces in the puzzle. This can lead to big problems because your doctor might give you the wrong treatment, which could even be life-threatening. So, keeping those puzzle pieces intact and accurate is really important.

- Availability: This one is about making sure your medical records are always ready when your doctor needs them. If the system that holds your records is down or not working, it's like your doctor trying to diagnose you in the dark. They need your medical history to make sure they're giving you the right treatment, so the information has to be available whenever it's needed. If it's not, it can lead to mistakes and make your diagnosis harder.

<h2></h2>

# DAD

<h2></h2>

# Fundamental Concepts of Security Models

Three Fundamental Concept of Security Models:

- Bell-LaPadula Model
- Biba Integrity Model
- Clark Wilson Model

<h2></h2>

<h3>Bell-LaPadula Model</h3>

Aims to achieve "Confidentiality" with 3 rules:

- Simple Security Property: Referred as `"no read up"`. If you're a lower-level agent, you can't look at classified information from higher-level agents. This stops lower-level folks from seeing top-secret stuff.
 
- Star Security Property: Referred as `"no write down"`. If you're a higher-level agent, you can't put secret info into documents meant for lower-level folks. This prevents secret leaks.
 
- Discretionary-Security Property: Uses `access Matrix` to control who can read and write operations. Example:
 
<p align="center">
<br/>
<img src="https://i.imgur.com/00QTLit.png" height="90%" width="90%" alt=""/>
<br />
  
Summarized: First two properties > "Write up, read down". Share confidential info with user with higher security clearance (write up), receive confidential information from user with lower security clearance (read down).

Limitation: `Not designed to handle file-sharing.`

<h2></h2>

<h3>Biba Integrity Model</h3>

Aims to achieve "Integrity" with 2 rules:

- Simple Integrity Property: Referred as `"no read down"`. If you're a super-secret agent with high-level access (higher integrity), you can't peek at or "read" less important stuff (lower integrity).

- Star Integrity Property: Referred as `"no write up"`. If you're just a regular agent with lower-level access (lower integrity), you can't mess with or "write" important stuff held by the big shots (higher integrity).

Summarized: "read up, write down". Biba is all about keeping information safe from tampering. Contrast with Bell-LaPadula Model.

Limitation: `Does not handle insider threat.`

<h2></h2>

<h3>Clask-Wilson Model</h3>

Aims to achieve integrity by using the following concepts:

- Constrained Data Item (CDI): Think of this as the important data we really want to keep safe and accurate, like a password or a top-secret document.

- Unconstrained Data Item (UDI): These are all the other types of data, like things you type into your computer or random bits of information that aren't super important.

- Transformation Procedures (TPs): These are like special rules or actions that we program into a computer, like "read" and "write." These rules make sure the important data (CDIs) stays safe and correct when we work with it.

- Integrity Verification Procedures (IVPs): These are like checks or tests that we run to make sure the important data (CDIs) is still reliable and hasn't been messed up. It's like making sure your password is still the right one.

<h2></h2>

