# Quiz 3

1. Which of the following factors evaluates a source to ensure it matches the use case?

- Relevancy

  - Relevancy ensures that a source matches its intended use case. Timelines ensures an intelligence source is up-to-date. Accuracy ensures an intelligence source produces effective results. Confidence Level ensures an intelligence source produces qualified statements about reliability.


2. In which phase of the security intelligence cycle is input collected from intelligence producers and consumers to improve the implementation of intelligence requirements?

- Feedback

  - The final phase of the security intelligence cycle is feedback and review, which utilizes the input of both intelligence producers and intelligence consumers. The goal of this phase is to improve the implementation of the requirements, collection, analysis, and dissemination phases as the life cycle is developed.


3. Which level of intelligence is directly used by Security Operations Center (SOC) staff to make real-time decisions in response to system alerts?

- Tactical

  - Tactical intelligence refers to the immediate, actionable information necessary for frontline staff, such as SOC analysts, to make decisions about real-time security threats and alerts.

#

# Quiz 4

1. Which step in the Lockheed Martin Kill Chain describes when an attacker combines the payload code with the exploit code so that the attack is ready to use?

- Weaponization

  - In Weaponization, the attacker couples the payload code, which enables access to the target, with the exploit code, which will exploit the vulnerability on the target's system. In Delivery, the attacker identifies a vector that can be used to transmit the weaponized code. In exploitation, the weaponized code is executed on the target system. In Installation, the weaponized code is run and persistence is achieved.


2. Which type of threat will patches NOT effectively combat as a security control?

- Zero-Day Attacks

  - Zero-day attacks have no known fix, so patches will not correct them. A zero-day vulnerability is a computer-software vulnerability that is unknown to, or unaddressed by, those who should be interested in mitigating the vulnerability (including the vendor of the target software). If a discovered software bug or known vulnerability is found, there is normally a patch or mitigation available for it. If a piece of malware has well-defined indicators of compromise, a patch or signature can be created to defend against it, as well.


3. In the Cyber Kill Chain model, at which stage does an attacker take advantage of a system's vulnerabilities using the malicious payload that has been delivered, thereby initiating the actual attack?

- Exploitation

  - The Exploitation phase is where the attacker leverages a vulnerability to execute the main part of the attack.
 
#

# Quiz 5 

1. What is the utilization of insights gained from threat research and threat modeling to proactively discover evidence of adversarial TTPs within a network or system called?

- Threat Hunting

  - Threat hunting is the utilization of insights gained from threat research and threat modeling to proactively discover evidence of adversarial TTPs within a network or system.

2. Which of the following is a characteristic of the Deep Web?

- Has info not indexed by standard search engines

  - The Deep Web contains information that is not indexed by standard search engines, making it invisible to conventional searches.

3. A cybersecurity analyst is reviewing the logs of a proxy server and saw the following URL, https://www.google.com/search?q=*%40diontraining.com. Which of the following is true about the results of this search?

- Returns all webpages containing email addressw affiliated with diontraining.com

  - %40 = @
  - Google interprets this statement as @diontraining.com and understands that the user is searching for email addresses since %40 is the hex code for the @ symbol. The * is a wild card character meaning that any text could be substituted for the * in the query. This type of search would provide an attacker with a list of email addresses associated with diontraining.com, and therefore could be used as part of a spear-phishing campaign.

#

# Quiz 6

1. Which tool allows for the creation of graphs to visualize network traffic flows through router and switch interfaces by utilizing SNMP

- MRTG 
  - A Multi Router Trafic Grapher is used for graphing traffic trends on network links and is particularly useful for spotting unusual traffic patterns.

2. You are a cybersecurity analyst investigating a potential network issue at your company. You suspect there is unusual traffic on your company's network. Which of the following would be most effective command-line for capturing and analyzing network packets in real-time to investigate this issue?

- tcpdump
  - tcpdump is a powerful command-line tool used for capturing and analyzing network packets in real-time, which would be effective for investigating unusual network traffic.

3. You are a cybersecurity analyst at Dion Training Solutions and have been observing an unusual pattern in the company’s DNS logs. Over the past week, there has been a significant increase in NXDOMAIN responses, which indicates that numerous domain lookups are failing because the domains do not exist. Upon closer inspection, you notice repeated attempts to resolve domain names that follow no logical naming pattern and appear to be randomly generated. There are no signs of unusually high network traffic, and the domains being queried are not matching any known malware signatures in your database. Based on this scenario, which of the following is the MOST likely cause of the increase in NXDOMAIN responses in the organization's DNS logs?

- The network is likely infected with malware using a Domain Generation Algorithm (DGA).
  - The pattern described in the scenario is a classic behavior of malware that employs DGAs to communicate with command and control servers.

#

# Quiz 7

1. Jamario, a security analyst at Dion Training Solutions, has recently set up a Security Onion sensor to monitor the network segment that handles the company's critical data. After configuring the sensor to sniff the network traffic, Jamario observes a series of Snort alerts indicating repeated outbound SSH attempts to an unrecognized external IP address. Which of the following options BEST describes what Jamario should do next after observing the Snort alerts on Security Onion?

- Analyze the traffic content and the triggered IDS rule to assess the situation and take appropriate action.

  - Jamario needs to validate the threat by examining the content and understanding the rule logic before proceeding with a response.
 
2. Evaluate the following log entry:

-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=

Jan 11 05:52:56 lx1 kernel: iptables INPUT drop IN=eth0 OUT= MAC=00:15:5d:01:ca:55:00:15:5d:01:ca:ad:08:00 SRC=10.1.0.102 DST=10.1.0.10 LEN=52 TOS=0x00 PREC=0x00 TTL=128 ID=3988 DF PROTO=TCP SPT=2583 DPT=23 WINDOW=64240 RES=0x00 SYN URGP=0

-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=

- The packet was blocked inbound to the network'

  - Firewall log formats will vary by vendors, but this example is a commonly used format from the Linux iptable firewall tool. This log starts with the date and time of the event and provides some key pieces of information. For example, the word "drop" shows the action this log entry recorded. In this case, the firewall dropped a packet due to an ACL rule being applied. Also, you can see that the packet was detected on the inbound connection over eth0, so we know that packets are being scanned and blocked when they are headed inbound to the network.

3. You are reviewing a rule within your organization's IDS. You see the following output:

-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=

alert tcp $EXTERNAL_NET $HTTP_PORTS -> $HOME_NET any
msg: “BROWSER-IE Microsoft Internet Explorer
CacheSize exploit attempt”;
flow: to_client,established;
file_data;

    content:"recordset"; offset:14; depth:9;
    content:".CacheSize"; distance:0; within:100;
    pcre:"/CacheSize\s*=\s*/";
    byte_test:10,>,0x3ffffffe,0,relative,string;

max-detect-ips drop, service http;
reference:cve,2016-8077;
classtype: attempted-user;
sid:65535;rev:1;

-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=

Based on this rule, which of the following malicious packets would this IDS alert on?

- An inbound malicious TCP packet

  - The rule header is set to alert only on TCP packets based on the first line of this IDS rule. The flow condition is set as "to_client,established", which means that only inbound traffic will be analyzed against this rule and only inbound traffic for connections that are already established. Therefore, this rule will alert on an inbound malicious TCP packet only when the packet matches all the conditions listed in this rule. This rule is an example of a Snort IDS rule. For the exam, you do not need to be able to create your own IDS rules, but you should be able to read them and pick out data.
