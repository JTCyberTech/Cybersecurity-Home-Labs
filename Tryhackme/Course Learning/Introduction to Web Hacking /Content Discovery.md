# What Is Content Discovery?

- In web application security, "content" encompasses various elements such as files, videos, pictures, backups, and website features.

- Content discovery involves identifying elements not readily visible on a website, often unintentionally exposed to the public.
  - Examples of discoverable content include internal staff pages, older website versions, backup files, configuration files, and administration panels.
 
There are three main ways of discovering content on a website.

<h3>Manual Discovery:</h3>

- Involves human exploration and navigation of a website.
- Requires human intuition and direct interaction with the site's interface.
- Useful for uncovering content that may not be readily apparent.

<h3>Automated Discovery:</h3>

- Involves the use of software tools, scripts, or bots to explore a website.
- Can be more efficient for scanning large websites or repetitive tasks.
- Requires technical skills for creating and using automation tools.

<h3>OSINT (Open-Source Intelligence) Discovery:</h3>

- Relies on publicly available information from external sources.
- May involve data from social media, search engines, or other online resources.
- Provides a broader perspective by leveraging external data for website content discovery.

<h2></h2>

<h2>Questions</h2>

1. What is the Content Discovery method that begins with M?

`Manually`

2. What is the Content Discovery method that begins with A?

`Automated`

3. What is the Content Discovery method that begins with O?

`OSINT`


<h2></h2>

# Manual Discovery - Robots.txt

- Robots.txt is a document that instructs search engines on which website pages to include or exclude from search engine results.
- It can restrict access to specific website areas, like admin portals or customer files.
- Valuable for penetration testers as it reveals restricted website locations.
- Offers control over what content search engines can index and display.

<h2></h2>

Question: What is the directory in the robots.txt that isn't allowed to be viewed by web crawlers?

- Copy and paste `http://10.10.46.138/robots.txt` in the URL.

<p align="center">
<br/>
<img src="https://i.imgur.com/04kZteC.png" height="90%" width="90%" alt=""/>
<br />

Answer: `/staff-portal`

<h2></h2>

