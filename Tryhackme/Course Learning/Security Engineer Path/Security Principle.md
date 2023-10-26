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

- Confidentiality: You expect that your credit card info stays a secret, known only to the payment processor. If you think someone shady might get your credit card number on the site, you won't want to buy anything. And if there's a data breach, and your personal info gets out, the company will suffer big losses.

- Integrity: Let's say you fill in your order and an intruder messes with the shipping address. Your package goes to the wrong place. If the information isn't trustworthy, you won't want to shop there.

- Availability: To shop online, you need the store's website or app to work. If it's down or keeps giving you trouble, you'll probably give up and look for another store. Availability means the service needs to be up and running when you need it.

<h2></h2>

<h3>CIA as it relates to patient records and related systems:</h3>

- Confidentiality: Think of this like a secret vault for your medical records. Your healthcare provider has to keep your medical information private and can get into legal trouble if they spill the beans. It's like a locked diary that only you and your doctor should read.

- Integrity: Imagine your medical record is like a puzzle, and each piece represents a part of your health history. If someone messes with those puzzle pieces, either by accident or on purpose, it's like putting the wrong pieces in the puzzle. This can lead to big problems because your doctor might give you the wrong treatment, which could even be life-threatening. So, keeping those puzzle pieces intact and accurate is really important.

- Availability: This one is about making sure your medical records are always ready when your doctor needs them. If the system that holds your records is down or not working, it's like your doctor trying to diagnose you in the dark. They need your medical history to make sure they're giving you the right treatment, so the information has to be available whenever it's needed. If it's not, it can lead to mistakes and make your diagnosis harder.

<h2></h2>

<h3>Authenticity and Nonrepudiation</h3>

- Authenitcity: means making sure something is real and not fake.
  - Example: imagine you're buying a fancy watch online. You want to be sure it's a real, genuine watch and not a cheap imitation. Authenticity in this case means being confident that the watch you're buying is indeed from the official company that makes it.
 
- Nonrepudiation: preventing someone from denying they did something. In things like online shopping, medical records, or banking transactions, nonrepudiation makes sure people can't later deny they made a purchase, received a diagnosis, or conducted a transaction.
  - Example: when you sign for a package delivery. The delivery person needs a record that you received it. Nonrepudiation ensures that you can't later say, "I didn't get the package," because your signature proves you did.

<h2></h2>

# DAD

Security of a system can be attacked through disclosure of secret data, alteration of data, or destruction of data.

- Disclosure: This is like spilling the beans, sharing a secret that should be kept. When confidential information is disclosed, it means someone has let out a secret they shouldn't have.
  - Example: Imagine if your friend tells everyone your surprise birthday party plans before the big day. Your surprise is ruined because the secret was disclosed.
 
- Alteration: This is like tampering with something to make it wrong or broken.
  - Example: If you draw a mustache on a picture, you've altered it. Now, the picture doesn't look the same, and it's not in its original, unaltered state.
 
- Destruction/Denial: making something disappear or preventing it from being available. When something is destroyed or denied, it means it's no longer there or not accessible when you need it.
  - Example: Think of your favorite toy. If it gets broken and you can't play with it anymore, it's like a form of destruction. If someone won't let you have your toy when you want to play with it, that's a kind of denial.
 
<h2></h2>

<h3>DAD with example of patient record and related system:</h3>

- Disclosure: It's like keeping a secret. Healthcare providers must keep your medical info private. If someone breaks in and shows your medical records to the world, it's a problem for the healthcare provider because they've lost control of the secret.

- Alteration: Think of this like changing a recipe in a cookbook. If a bad person tweaks your medical records, it's like giving the chef the wrong recipe. This could lead to the wrong treatment, and that's really bad, possibly even life-threatening.

- Destruction/Denial: Imagine a hospital going digital, like replacing paper with computers. If a troublemaker messes with the computers, it's like turning off all the lights in the hospital. They can't work properly, even if they go back to using paper. It's a big problem because the patient info won't be available, and everything comes to a halt.

Protection against disclosure, alteration, destruction/denial is equivalent to working to maintain the CIA.

Too much protection on confidentiality and integrity can restrict availability. Too much avaialability can result in losing confidentiality and integrity. Need to find a good balance between the three CIA.


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
  
Summarized: First two properties > "Read down, Write up". Share confidential info with user with higher security clearance (write up), receive confidential information from user with lower security clearance (read down).

Limitation: `Not designed to handle file-sharing.`

<h2></h2>

<h3>Biba Integrity Model</h3>

Aims to achieve "Integrity" with 2 rules:

- Simple Integrity Property: Referred as `"no read down"`. If you're a super-secret agent with high-level access (higher integrity), you can't peek at or "read" less important stuff (lower integrity).

- Star Integrity Property: Referred as `"no write up"`. If you're just a regular agent with lower-level access (lower integrity), you can't mess with or "write" important stuff held by the big shots (higher integrity).

Summarized: "Read up, Write down". Biba is all about keeping information safe from tampering. Contrast with Bell-LaPadula Model.

Limitation: `Does not handle insider threat.`

<h2></h2>

<h3>Clask-Wilson Model</h3>

Aims to achieve integrity by using the following concepts:

- Constrained Data Item (CDI): Think of this as the important data we really want to keep safe and accurate, like a password or a top-secret document.

- Unconstrained Data Item (UDI): These are all the other types of data, like things you type into your computer or random bits of information that aren't super important.

- Transformation Procedures (TPs): These are like special rules or actions that we program into a computer, like "read" and "write." These rules make sure the important data (CDIs) stays safe and correct when we work with it.

- Integrity Verification Procedures (IVPs): These are like checks or tests that we run to make sure the important data (CDIs) is still reliable and hasn't been messed up. It's like making sure your password is still the right one.

<h2></h2>

# Defence-In Depth

Create a security system that have multiple layers or level. `Multi-Level Secuirty`

Imagine you have a special drawer with important things inside, and you want to protect them from burglars. It's not enough to just lock the drawer. You'd also want to lock the room where the drawer is, lock the main door to your place, and even have security cameras. By adding these layers of security, you make it harder for thieves to get to your stuff. While it might not stop every thief, it will definitely make most of them give up and slow down the rest.

<h2></h2>

# ISO/IEC 19249

ISO: International Organization for Standardization 
IEC: International Electrotechnical Commission

Both came up with the ISO/IEC 19249::2017 Information technology - Security techniques - Catalogue of architectural and design principles for secure products, systems and applications.

<h2></h2>

<h3>ISO/IEC 19249 lists five architectural principles:</h3>

- Domain Separation, Layering, Encapsulation, Redundancy, and Virtualization.

<h3>ISO/IEC 19249 teaches five design principles:</h3>

- Least Privilege, Attack Surface Minimisation, Centralized Parameter Validation, Centralized General Security Services, and Preparing for Error and Exception Handling.

<h2></h2>

# Zero Trust versus Trust but Verify

- Trust but Verify: This idea means you should always double-check, even if you trust someone or something. For example, imagine you trust a friend to look after your pet. You should still ask for updates or check the security camera to make sure everything is okay. It's not always possible to check everything by hand, like monitoring every website visited by a user. So, you use automated security tools like a home security system.

- Zero Trust: This principle treats trust as a weakness, especially when dealing with inside jobs. Instead of trusting right away, it suggests you should never trust anyone or anything until they prove themselves. It's like saying, "Show me you're trustworthy." Unlike old models that trusted things based on their location or owner (like letting people in your house because they're family), zero trust requires checking who or what it is every time. You need proof (authentication and authorization) before letting anyone or anything access your stuff. If there's ever a security breach, using the zero trust approach means the damage will be limited because you didn't trust blindly in the first place.

<h3></h3>

#  Threat versus Risk

- Vulnerability: having a weak spot that could be attacked or harmed. In information security, it's a point of weakness that needs protection.
  - Example: An unlocked door is a vulnerability in home security. It's a weak spot that could allow a thief to enter.

- Threat: the danger that comes with a vulnerability. It's like the bad thing that could happen because of the weak spot.
  - Example: In the case of the unlocked door, the threat is a potential burglary. The danger is the thief getting inside.
  
- Risk: about how likely it is that the threat will actually take advantage of the vulnerability and what the consequences will be.
  -  Example: If you live in a very safe neighborhood, the risk of a burglary due to the unlocked door might be low. But if you're in a high-crime area, the risk is higher, and the impact (consequences) of a break-in could be significant, like loss of valuable items or property damage.
