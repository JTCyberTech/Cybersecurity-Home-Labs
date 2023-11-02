# Introduction

- This room provides a foundational understanding of the Burp Suite web application security testing framework.
- Focus areas include:
  - Thorough introduction to Burp Suite.
  - Comprehensive overview of the tools available within the framework.
  - Detailed guidance on installing Burp Suite on your system.
  - Navigating and configuring Burp Suite.
- The core of the Burp Suite framework is the Burp Proxy, which will be introduced.
- This room emphasizes theoretical content and serves as a foundational resource.
- If you haven't used Burp Suite before, it's recommended to read and actively engage with the provided information.
- Experimentation is crucial for grasping the fundamentals of this framework.
- Combining the knowledge presented with hands-on exploration will establish a strong foundation for utilizing Burp Suite effectively in future rooms.


<h2></h2>

# What is Burp Suite

- Burp Suite is a Java-based framework for web application penetration testing, serving as an industry-standard tool for security assessments.
- It captures and manipulates HTTP/HTTPS traffic between browsers and web servers, making it valuable for manual testing.
- Burp Suite has different editions, including Community (free), Professional, and Enterprise.
- Burp Suite Professional offers advanced features like an automated scanner, fuzzer, and integration capabilities.
- Burp Suite Enterprise is used for continuous scanning of web applications, residing on a server.

Answers to Questions:

Which edition of Burp Suite runs on a server and provides constant scanning for target web apps?

`Burp Suite Enterprise`

Burp Suite is frequently used when attacking web applications and ______ applications.

`mobile`


<h2></h2>

# Features of Burp Community

Burp Suite Community Features:

- Proxy: Allows interception and modification of web application requests and responses.
- Repeater: Captures, modifies, and resends requests, ideal for testing payloads and endpoint vulnerabilities.
- Intruder: Sprays endpoints with requests, useful for brute-force attacks or endpoint fuzzing.
- Decoder: Transforms data by decoding captured information or encoding payloads efficiently.
- Comparer: Compares two pieces of data at the word or byte level, speeding up the comparison process.
- Sequencer: Evaluates the randomness of tokens like session cookies, exposing potential vulnerabilities in data generation algorithms.
- Extensibility: Burp Suite Community supports extensions in Java, Python (via Jython interpreter), or Ruby (via JRuby interpreter).
- Burp Suite Extender: Easily loads extensions into the framework to enhance functionality.
- BApp Store (Marketplace): Access third-party modules to extend Burp Suite's capabilities.
- Logger++ Extension: Example of an available extension that enhances logging functionality in Burp Suite.

Answers to Questions:

Which Burp Suite feature allows us to intercept requests between ourselves and the target?

`Proxy`

Which Burp tool would we use to brute-force a login form?

`Intruder`


<h2></h2>

# Installation

Installing Burp Suite:

- Burp Suite is a versatile tool useful for web and mobile application assessments, penetration testing, bug bounty hunting, and web app development debugging.
- If you're using the AttackBox, Burp Suite is pre-installed, so you don't need to install it separately.
- To download Burp Suite for various platforms:
  - Visit the Burp Suite download page for the latest version.
  - For Kali Linux, it's pre-installed, or you can install it from the Kali apt repositories.
  - For Linux, macOS, and Windows, PortSwigger provides dedicated installers for Burp Suite Community and Burp Suite Professional.
    - Select your operating system from the dropdown menu on the Burp Suite downloads page.
    - Choose Burp Suite Community Edition and click Download.
   
<h2></h2>

Installation:

- Install Burp Suite using the appropriate method for your operating system.
  - On Windows, run the executable file.
  - On Linux, execute the installation script from the terminal, with or without sudo.
  - Without sudo on Linux, Burp Suite will be installed in your home directory at `~/BurpSuiteCommunity/BurpSuiteCommunity` and won't be added to your PATH.
  - The installation wizard provides clear instructions, and it's generally safe to accept the default settings, but reviewing the installer is recommended.
- After successfully installing Burp Suite, you can proceed to launch the application and explore initial setup and configuration in the next step.


<h2></h2>

# The Dashboard

- Use the pre-installed Burp Suite Community Edition in the AttackBox.
- Launch the AttackBox by clicking the "Start AttackBox" button.
- Accept terms and conditions when launching Burp Suite.
- Select a project type (limited options in Burp Suite Community).
- Recommended to keep default configuration settings.
- Click "Start Burp" to open the Burp Suite interface.
- Consider going through training materials when prompted.
- If no training, you'll see the Burp Dashboard.
- The Burp Dashboard is divided into four quadrants.

<p align="center">
<br/>
<img src="https://i.imgur.com/sCA08e1.png" height="90%" width="90%" alt=""/>
<br />

Tasks:

- The Tasks menu in Burp Suite allows users to define background tasks that the application will perform.
- In Burp Suite Community, the default "Live Passive Crawl" task is available, which automatically logs visited pages.
- Burp Suite Professional offers advanced features such as on-demand scans for more comprehensive testing.


Event log:

- The Event log in Burp Suite provides valuable information about various actions and events within the application.
- It includes details about starting the proxy and information about connections made through Burp, offering insights into network activity.


Issue Activity:

- The Issue Activity section is a feature exclusive to Burp Suite Professional.
- It presents a list of vulnerabilities identified by the automated scanner, ranked by severity.
- Users can filter the issues based on the certainty of the vulnerability, making it easier to focus on critical security concerns.


Advisory:

- The Advisory section in Burp Suite contains in-depth information about identified vulnerabilities.
- It includes references to related resources and suggested remediations for addressing the vulnerabilities.
- Users can export this information into a report for documentation and communication purposes.
- Notably, in Burp Suite Community, this section may not display any vulnerabilities, as it is a feature primarily available in the Professional edition.

<h2></h2>

Using Help Icons in Burp Suite:

- In Burp Suite, there are question mark icons scattered throughout the software's various tabs and windows.

Accessing Helpful Information:

- You can click on these question mark icons to access valuable information related to the specific section you're working in.

Utilize for Assistance and Clarification:

- These help icons serve as a crucial resource when you need assistance or clarification regarding a particular feature or function within Burp Suite.

Maximizing Effectiveness:

- To make the most of your experience with Burp Suite, ensure you effectively use these help icons to guide you when needed.

Exploring the Help Menu:

- When you click on the question mark logo, it opens a new window providing insights, tips, and explanations related to the features or functions of Burp Suite.

Gradual Familiarity with Burp Suite:

- As you explore the various tabs and functionalities of Burp Suite, you will progressively become more familiar with its capabilities and how to use them effectively.

<h2></h2>

Answers to Questions:

What menu provides information about the actions performed by Burp Suite, such as starting the proxy, and details about connections made through Burp?

`Event Log`


<h2></h2>

# Navigation

<h3>Module Selection:</h3>

- Top menu bars in Burp Suite provide access to different modules.
- You can easily switch between modules by clicking on the corresponding module name.
- For example, you can select the "Burp Proxy" module from the top menu bar.

<h3>Sub-Tabs:</h3>

- Within each selected module, you may find multiple sub-tabs that contain specific settings and options.
- These sub-tabs appear in a second menu bar directly below the main menu bar.
- You can navigate to the sub-tab of your choice by clicking on it.
- For instance, within the "Burp Proxy" module, you might choose the "Proxy Intercept" sub-tab.

<h3>Detaching Tabs:</h3>

- If you prefer to work with multiple tabs in separate windows for easier organization, Burp Suite allows you to detach tabs.
- To detach a tab, go to the "Window" option in the application menu, which is located above the Module Selection bar.
- From the "Window" menu, select "Detach," and the currently selected tab will open in a separate window.
- Detached tabs can later be reattached to the main Burp Suite interface using the same method.

<h2></h2>

Burp Suite also provides keyboard shortcuts for quick navigation to key tabs. By default, the following shortcuts are available:

- `Ctrl + Shift + D`:	Dashboard
- `Ctrl + Shift + T`:	Target tab
- `Ctrl + Shift + P`:	Proxy tab
- `Ctrl + Shift + I`:	Intruder tab
- `Ctrl + Shift + R`:	Repeater tab

<h2></h2>

Answers to Questions:

Which tab Ctrl + Shift + P will switch us to?

`Proxy tab`

