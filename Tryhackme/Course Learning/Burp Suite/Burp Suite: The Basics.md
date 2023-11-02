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


<h2></h2>

# Options

- Burp Suite Configuration: Before using Burp Proxy, it's essential to understand and configure Burp Suite settings, which come in two types: Global (User) settings and Project settings.

- Global Settings: Global settings affect the entire Burp Suite installation and provide a baseline configuration. These settings are applied every time you start the application.

- Project Settings: Project settings are specific to the current project and are only applicable during the session. Note that Burp Suite Community Edition does not support saving projects.

- Accessing Settings: To access the settings, click the Settings button in the top navigation bar, which opens a separate settings window.

- Settings Window: The settings window displays various settings options and can be navigated through a left-hand menu, which includes features like searching, type filtering, and selecting by categories.

- Search Feature: The search feature allows for quick and easy lookup of specific settings using keywords, streamlining the configuration process.

- Shortcuts: Many tools in Burp Suite provide shortcuts to specific categories of settings. For example, the Proxy module has a Proxy settings button for quick access to proxy-related options.

- Familiarization: It's recommended to spend some time familiarizing yourself with the range of configurable options within Burp Suite before proceeding with exercises related to configuring its settings.

<h2></h2>

Answers to Questions:

In which category can you find a reference to a "Cookie jar"?

`Sessions`

In which base category can you find the "Updates" sub-category, which controls the Burp Suite update behaviour?

`Suite`

What is the name of the sub-category which allows you to change the keybindings for shortcuts in Burp Suite?

`Hotkeys`

If we have uploaded Client-Side TLS certificates, can we override these on a per-project basis (yea/nay)?

`yea`


<h2></h2>

# Introduction to the Burp Proxy

<h3>Burp Proxy Overview:</h3>

- Burp Proxy is a vital component of Burp Suite, used for capturing requests and responses between the user and the target web server.
- It allows for the interception, manipulation, and forwarding of web traffic.
- Intercepted traffic can be sent to other Burp modules or allowed to continue to its destination.

<h3>Intercepting Requests:</h3>

- When requests pass through Burp Proxy, they are intercepted and held back from reaching the target server.
- Intercepted requests can be managed in the Proxy tab, enabling actions like forwarding, dropping, editing, or sending them to other Burp modules.
- The "Intercept is on" button enables or disables the request interception.

<h3>Taking Control:</h3>

- Intercepting requests provides testers with complete control over web traffic, making it invaluable for testing web applications.

<h3>Capture and Logging:</h3>

- Burp Suite captures and logs requests by default, even when interception is turned off.
- This logging feature is useful for later analysis and review of previous requests.

<h3>WebSocket Support:</h3>

- Burp Suite also captures and logs WebSocket communication, enhancing web application analysis capabilities.

<h3>Log and History:</h3>

- Captured requests can be viewed in the HTTP history and WebSockets history sub-tabs, facilitating retrospective analysis and interaction with other Burp modules.
 
<h3>Proxy Settings:</h3>

- Proxy-specific options can be accessed by clicking the Proxy settings button, providing extensive control over the Proxy's behavior and functionality.

<h3>Notable Features in Proxy Settings:</h3>

- Response Interception: By default, the proxy doesn't intercept server responses unless explicitly requested on a per-request basis.
- The "Intercept responses based on the following rules" checkbox, along with defined rules, allows for flexible response interception.
- Match and Replace: The "Match and Replace" section in Proxy settings allows the use of regular expressions (regex) to modify incoming and outgoing requests.
- This feature is useful for dynamic changes like modifying the user agent or manipulating cookies.

<h3>Optimizing Usage:</h3>

- Familiarize yourself with the Proxy-specific options to optimize your Burp Proxy usage.
- Experiment with the settings and options to enhance your understanding and proficiency with the tool.


<h2></h2>

# Introduction to the Burp Proxy

1. Burp Proxy's Role in Burp Suite:

- Burp Proxy is a fundamental and essential component of Burp Suite.
- It facilitates the capture of requests and responses between the user and the target web server.

2. Intercepting Requests:

- When requests are sent through Burp Proxy, they are intercepted and held back from reaching the target server.
- Intercepted requests are visible in the Proxy tab, allowing for various actions like forwarding, editing, dropping, or sending them to other Burp modules.
- Clicking the "Intercept is on" button disables interception to let requests pass through without interruption.

3. Testers' Empowerment:

- Intercepting requests provides testers with complete control over web traffic, making it a valuable tool for testing web applications.

4. Capture and Logging:

- Burp Suite automatically captures and logs requests made through the proxy, even when interception is turned off.
- This logging feature is useful for later analysis and reviewing previous requests.

5. WebSocket Support:

- Burp Suite also captures and logs WebSocket communication, enhancing the ability to analyze web applications.

6. Logs and History:

- Captured requests can be viewed in the HTTP history and WebSockets history sub-tabs.
- This allows for retrospective analysis and the ability to send requests to other Burp modules as needed.

7. Proxy Settings Control:

- Proxy-specific options can be accessed by clicking the Proxy settings button.
- These settings offer extensive control over the Proxy's behavior and functionality.

8. Response Interception:

- By default, the proxy does not intercept server responses unless explicitly requested on a per-request basis.
- The "Intercept responses based on the following rules" checkbox, along with defined rules, provides flexibility for response interception.

9. Match and Replace:

- The "Match and Replace" section in Proxy settings allows the use of regular expressions (regex) to modify incoming and outgoing requests.
- This feature enables dynamic changes, such as modifying the user agent or manipulating cookies, for testing and analysis.
