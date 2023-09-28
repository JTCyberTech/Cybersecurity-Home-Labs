<p align="left">
<br/>
<img src="https://i.imgur.com/iOs8wPS.gifv" height="100%" width="100%" alt=""/>
<br />

<h2>Description:</h2>


I will establish a cloud-based Security Information and Event Management (SIEM) system using Azure Sentinel, using a Virtual Machine to function as a honeypot. The honeypot serves as a deceptive system or network engineered to entice potential attackers, aiming to collect insights into their methodologies, strategies, and motives. This information aids cybersecurity professionals in gaining a deeper understanding of potential threats and bolstering defense mechanisms.

I will closely monitor the logs of attempted intrusions on the honeypot, particularly focusing on scrutinizing failed Remote Desktop Protocol (RDP) login attempts. Subsequently, I will present a visual representation of the geographic origins of these attackers on a world map, facilitating the analysis of attack source locations.

<h2></h2>

<h2>Setup Overview</h2>

- Create Azure with a free subscription that has 200 dollars of free credits.
  
- Create a Virtual Machine in Azure that is extremely vulnerable to the internet and anyone with a device can ping it by turning off all the firewalls.

- Create a log analytics workspace with a log repository in Azure to process and analyze our logs from the virtual machine.

- Set up Azure Sentinel within Azure and create a map that analyzes the attacks from all over the world on our honeypot.

- Powershell will be used to extract the IP Addresses from the honeypot in the Windows Log and convert them into latitude and longitude with a third-party API.
- Create a custom log with geographic data in the VM with the latitude and longitude logs.

<h2></h2>

<h2>Key Reasons of Implementing SIEM</h2>

- Log Management: SIEM centralizes log management, making it easier to collect, store, and analyze logs from various sources across an organization's IT infrastructure.

- Threat Detection and Response: SIEM systems provide real-time monitoring and analysis of security events, enabling the rapid detection of threats and immediate response to mitigate potential damage.

- Incident Investigation: SIEM tools offer advanced search and correlation capabilities, aiding in detailed forensic analysis during incident investigations. This is crucial for understanding the scope and impact of security incidents.

- Security Automation: Many SIEM platforms support automated responses to specific security events, reducing the response time and minimizing human error.

- User Activity Monitoring: SIEM solutions provide insights into user behavior and activities, helping organizations detect insider threats, unauthorized access, and abnormal user patterns.

- Alert Prioritization: SIEM can create security alerts, allowing the security team to focus on the most critical threats and reducing alert fatigue.

