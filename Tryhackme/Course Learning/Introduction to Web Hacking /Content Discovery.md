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

# Manual Discovery - Favicon

Favicon is a small icon for website branding. It appears in the browser's address bar or tab

<p align="center">
<br/>
<img src="https://i.imgur.com/5LVvRnQ.png" height="90%" width="90%" alt=""/>
<br />

- Frameworks used to build websites may include default favicons as part of their installation.
- Failure to replace the default favicon with a custom one can reveal the framework being used.
- Website developers should ensure they replace default favicons to maintain a professional and customized appearance.
- OWASP host a database of common framework icons that you can use to check against the targets favicon [Wiki](https://wiki.owasp.org/index.php/OWASP_favicon_database)
- Once we know the framework stack, we can use external resources to discover more about it.


<h2></h2>

<h2>Question</h2>

<h3>Question 1: What framework did the favicon belong to?</h3>

- Navigate to this site: https://static-labs.tryhackme.cloud/sites/favicon/
  - We can see that there is a favicon for the webpage.


<p align="center">
<br/>
<img src="https://i.imgur.com/b5LfIbx.png" height="90%" width="90%" alt=""/>
<br />
 
- Right-click the page and select "View Page Source".

<p align="center">
<br/>
<img src="https://i.imgur.com/RrVObiS.png" height="90%" width="90%" alt=""/>
<br />

- Click on the icon link.

<p align="center">
<br/>
<img src="https://i.imgur.com/0ys2fFa.png" height="90%" width="90%" alt=""/>
<br />

- Right-click on the icon. And "Save Image As" to the VM.

<p align="center">
<br/>
<img src="https://i.imgur.com/K8gOPAI.png" height="90%" width="90%" alt=""/>
<br />

- Go to your download folder. Right-click the icon, select "Properties".

<p align="center">
<br/>
<img src="https://i.imgur.com/4usobne.png" height="90%" width="90%" alt=""/>
<br />

- Go to "Digests" tab. Make sure "MD5" is checked. Check on "HasH".

<p align="center">
<br/>
<img src="https://i.imgur.com/mb82gmy.png" height="90%" width="90%" alt=""/>
<br />

- We got our MD5 hash. Right-click on it and Copy it.

<p align="center">
<br/>
<img src="https://i.imgur.com/EgASSsZ.png" height="90%" width="90%" alt=""/>
<br />

- Navigate to the OWASP Favicon Database site: https://wiki.owasp.org/index.php/OWASP_favicon_database.
  - Press `Ctrl + F` to search, and paste the MD5 key into the search bar.

<p align="center">
<br/>
<img src="https://i.imgur.com/EgASSsZ.png" height="90%" width="90%" alt=""/>
<br />
  
- Got the Answer for the framework.

<p align="center">
<br/>
<img src="https://i.imgur.com/XYuhZvG.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

<h2>Another way to get the MD5 hash</h2>

- Copy the link for favicon. (Without: View-source)
  - `https://static-labs.tryhackme.cloud/sites/favicon/images/favicon.ico`

<p align="center">
<br/>
<img src="https://i.imgur.com/QMN3dbM.png" height="90%" width="90%" alt=""/>
<br />

- Open Terminal and use `curl` command.
  - curl [link] | md5sum
  - `curl  https://static-labs.tryhackme.cloud/sites/favicon/images/favicon.ico | md5sum`
 
<p align="center">
<br/>
<img src="https://i.imgur.com/9RnxRmK.png" height="90%" width="90%" alt=""/>
<br />

- Got the hash, so we can go on the OWASP Favicon Database to search for the framework.

<p align="center">
<br/>
<img src="https://i.imgur.com/MkBnTkN.png" height="90%" width="90%" alt=""/>
<br />

Answer: `cgiirc`

<h2></h2>

# Manual Discovery - Sitemap.xml

<h3>Question: What is the path of the secret area that can be found in the sitemap.xml file?</h3>

- Navigate to the site that question asked with your VM: `http://10.10.152.178/sitemap.xml`.
  - Found the path.

<p align="center">
<br/>
<img src="https://i.imgur.com/cD8f8zd.png" height="90%" width="90%" alt=""/>
<br />
 
Answer: `/s3cr3t-area`

<h2></h2>

# Manual Discovery - HTTP Headers

- Open Terminal and use the `curl` command with `-v`, this option makes the fetching more verbose/talkative.
  - `curl 10.10.152.178 -v`

<p align="center">
<br/>
<img src="https://i.imgur.com/LPBqZS3.png" height="90%" width="90%" alt=""/>
<br />

- Scroll through the output and find the flag.

<p align="center">
<br/>
<img src="https://i.imgur.com/HmgrXg8.png" height="90%" width="90%" alt=""/>
<br />

Answer: `THM{HEADER_FLAG}`


<h2></h2>

# Manual Discovery - Framework Stack

<h3>Question: What is the flag from the framework's administration portal?</h3>

- Navigate to the site that question asked with your VM: `https://static-labs.tryhackme.cloud/sites/thm-web-framework`.
  - Click on the Documentation tab.
  - From the Documentation tab, found information about new path with username and password.

<p align="center">
<br/>
<img src="https://i.imgur.com/FjELqUS.png" height="90%" width="90%" alt=""/>
<br />
 
- Navigate to the new path and put in the username and password. Then click on Login.
  - `http://10.10.152.178/thm-framework-login`

<p align="center">
<br/>
<img src="https://i.imgur.com/SStK3th.png" height="90%" width="90%" alt=""/>
<br />

- Found the flag from the framework's administration portal.

<p align="center">
<br/>
<img src="https://i.imgur.com/IvbSMFu.png" height="90%" width="90%" alt=""/>
<br />

Answer: `THM{CHANGE_DEFAULT_CREDENTIALS}`

<h2></h2>

# OSINT - Google Hacking / Dorking

- OSINT (Open-Source Intelligence) resources are freely available tools for collecting information about target websites.
- These external resources can aid in discovering valuable data about the target site.
- OSINT tools provide a cost-effective and accessible means of gathering intelligence.
- Utilizing OSINT is essential for enhancing your knowledge and understanding of a target website.

<h2></h2>

<h2>Google Hacking / Dorking</h2>

- Google hacking, also known as Dorking, leverages advanced Google search features to find custom content.
- The `site:` filter allows you to target results from a specific domain, like "site:tryhackme.com."
- You can refine your search by adding keywords, such as "site:tryhackme.com admin," to find pages containing specific terms on the specified domain.
- Google hacking allows you to combine multiple filters and search parameters for precise results.

<p align="center">
<br/>
<img src="https://i.imgur.com/ob4TZfl.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

<h2>Question</h2>

Question 1: What Google dork operator can be used to only show results from a particular site?

Answer: `site:`

<h2></h2>

# OSINT - Wappalyzer

- Wappalyzer is an online tool and browser extension.
- It identifies the technologies used by a website.
- Technologies include frameworks, CMS, payment processors, and more.
- Wappalyzer can also discover version numbers of these technologies.

Website: https://www.wappalyzer.com/

<h2></h2>

<h2>Question</h2>

Question 1: What online tool can be used to identify what technologies a website is running?

Answer: `Wappalyzer`

<h2></h2>

# OSINT - Wayback Machine

- The Wayback Machine is a historical website archive dating back to the late 90s.
- It allows you to search for a domain name and view snapshots of the website from various points in time.
- It's a valuable tool for researching the history of websites and tracking changes over time.
- Useful for uncovering old pages that may still exist on a current website.

<h2></h2>

<h2>Question</h2>

Question 1: What is the website address for the Wayback Machine?

Answer: `https://archive.org/web/`

<h2></h2>

<h2>OSINT - GitHub</h2>

- Git is a `version control system for` tracking changes in projects.
- Git facilitates teamwork by allowing visibility into team members' edits and file changes.
- Users commit changes with messages and push them to a central repository.
- GitHub is an online hosting platform for Git repositories.
- Repositories on GitHub can be public or private with access controls.
- GitHub's search feature helps find specific repositories.
- Discovering repositories on GitHub can lead to source code and other valuable content.

<h2></h2>

<h2>Question</h2>

Question 1: What is Git?

Answer: `version control system`

<h2></h2>

# OSINT - S3 Buckets

- S3 Buckets: Amazon AWS storage service for files and static website content in the cloud.
- Access Permissions: Owners can set files to be public, private, or writable.
- Security Risk: Misconfigured permissions can expose private files to the public.
- S3 Bucket URL Format: http(s)://{name}.s3.amazonaws.com (e.g., tryhackme-assets.s3.amazonaws.com).
- Discovery Methods: S3 buckets can be found in website source code, GitHub repositories, or through automation.
- Automation: Common automation method involves using company name with common terms like {name}-assets, {name}-www, {name}-public, {name}-private, etc.

<h2></h2>

<h2>Question</h2>

Question 1: What URL format do Amazon S3 buckets end in?

Answer: `.s3.amazonaws.com`


<h2></h2>

# Automated Discovery

<h3>What is Automated Discovery?</h3>

- Automated discovery uses tools to find content, replacing manual searches.
- It involves making numerous requests to web servers, often in large quantities.
- These requests determine the existence of files or directories on websites.
- Wordlists are essential resources enabling this automated discovery process.

<h3>What are wordlists?</h3>

- Wordlists are text files with commonly used words.\
- Wordlists serve various purposes, like password or content searching.
- For content searching, use wordlists with common directory and file names.
- A recommended resource for wordlists is https://github.com/danielmiessler/SecLists curated by Daniel Miessler.

<h3>Automation Tools</h3>

- Multiple content discovery tools are available, each with their unique features and limitations.
- This discussion will focus on three preinstalled tools: `ffuf`, `dirb`, and `gobuster`.
- These tools are readily available on our attack box for content discovery purposes.

<h2></h2>

Using ffuf:

- `ffuf -w /usr/share/wordlists/SecLists/Discovery/Web-Content/common.txt -u http://10.10.152.178/FUZZ`

Using dirb:

- `dirb http://10.10.152.178/ /usr/share/wordlists/SecLists/Discovery/Web-Content/common.txt`

Using Gobuseter:

- `gobuster dir --url http://10.10.152.178/ -w /usr/share/wordlists/SecLists/Discovery/Web-Content/common.txt`

<h2></h2>

<h2>Question</h2>

Question 1: What is the name of the directory beginning "/mo...." that was discovered?

Answer: `/monthly`

Question 2: What is the name of the log file that was discovered?

Answer: `/development.log`
