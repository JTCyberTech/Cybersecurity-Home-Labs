# CIA

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

