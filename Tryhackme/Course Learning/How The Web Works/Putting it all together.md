# Putting It All Together

- Requesting a webpage involves several behind-the-scenes processes.
- Your computer uses DNS to find the server's IP address.
- The HTTP protocol is used for communication between your computer and the web server.
- The web server returns various elements like HTML, JavaScript, CSS, and images.
- Your browser formats and displays the website using these elements.

<h2></h2>

# Other Components

<h3>Load Balancers</h3>

- Load balancers are essential for handling high traffic websites and ensuring high availability of applications.
- They distribute incoming requests to multiple servers, improving performance and preventing overloading a single server.
- Load balancers use various algorithms, such as round-robin and weighted, to determine which server should handle each request.
- `Health checks` are performed by load balancers to ensure server reliability, and they stop sending traffic to unresponsive servers until they recover.

<p align="center">
<br/>
<img src="https://i.imgur.com/YTJTNk5.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

<h3>CDN (Content Delivery Networks)</h3>

- CDN reduces website traffic by hosting static files (JavaScript, CSS, Images, Videos) on servers worldwide.
- Content is distributed across thousands of servers for efficient global delivery.
- CDN locates the nearest server to the user for faster content access.

<h2></h2>

<h3>Databases</h3>

- Websites require a method to store user information.
- Webservers interact with databases for data storage and retrieval.
- Databases vary in complexity, from simple plain text files to advanced server clusters.
- Common databases include MySQL, MSSQL, MongoDB, GraphQL, and Postgres, each with unique features.

<h2></h2>

<h3>WAF (Web Application Firewall)</h3>

- Web Application Firewall (WAF) acts as a protective barrier between web requests and the web server.
- Its primary function is to safeguard the web server from hacking and denial of service attacks.
- WAF analyzes web requests to detect common attack techniques and distinguish between real browsers and bots.
- It employs rate limiting to restrict the number of requests from an IP address per second.
- If a request is identified as a potential attack, the WAF will block it and prevent it from reaching the web server.


<h2></h2>

<h2>Questions</h2>

1. What can be used to host static files and speed up a clients visit to a website?

`CDN`

2. What does a load balancer perform to make sure a host is still alive?

`Health Check`

3. What can be used to help against the hacking of a website?

`WAF`


<h2></h2>

# How Web servers work.

<h3>What is a Web Server?</h3>

- A web server is software that uses the HTTP protocol to deliver web content to clients by listening for incoming connections.
- Common web server software includes Apache, Nginx, IIS, and NodeJS.
- Web servers deliver files from their root directory, defined in software settings.
- Example root directories include /var/www/html for Nginx and Apache on Linux, and C:\inetpub\wwwroot for IIS on Windows.
- When you request a file, the web server sends the corresponding file from its local storage.

<h2></h2>

<h3>Virtual Hosts</h3>

- Web servers use virtual hosts to host multiple websites with different domain names.
- The web server checks the hostname in HTTP headers and matches it with virtual hosts' configurations.
- If a match is found, the corresponding website is served; otherwise, the default website is provided.
- Virtual hosts can map their root directories to different locations on the hard drive.
- This allows websites like one.com to be mapped to /var/www/website_one and two.com to /var/www/website_two.
- There's no limit to the number of different websites a web server can host.

<h2></h2>

<h3>Static Vs Dynamic Content</h3>

Static content:

- Content that never changes.
  - Examples: images, JavaScript, CSS, and unchanging HTML.
- Directly served from the webserver with no modifications.

Dynamic content:

- Content that can change with different requests.
  - Examples: blog homepage with latest entries, search results on a blog.
- Changes are made in the Backend using programming and scripting languages.

Backend vs. Frontend:

- Backend handles processing behind the scenes, not visible in HTML source.
- Frontend presents the result of Backend processing, what you see in your browser.


<h2></h2>

<h3>Scripting and Backend Languages</h3>

- Backend languages like PHP, Python, Ruby, NodeJS, and Perl make websites interactive for users.
- They can interact with databases, call external services, and process user data.
- These languages enable dynamic web functionality, such as generating personalized content based on user input.
  - Example: In PHP, you can request a website like http://example.com/index.php?name=adam to process user input.


<h2></h2>

If index.php was built like this: `<html><body>Hello <?php echo $_GET["name"]; ?></body></html>`

It would output the following to the client: `<html><body>Hello adam</body></html>`

<h2></h2>

<h2>Questions</h2>

1. What does web server software use to host multiple sites?

`Virtual Host`

2. What is the name for the type of content that can change?

`Dynamic`

3. Does the client see the backend code? Yay/Nay

`Nay`

<h2></h2>

<h2>Order of How a Request to a Website Works</h2>

1. Request tryhackme.com in yout browser.

2. Check Local Cache for IP Address.

3. Check your recursive DNS Server for Address.

4. Query root esrver to find authoritative DNS Server.

5. Authoritative DNS server advises the IP address for the website.

6. Request passes through a Web Application Firewall.

7. Request passes through a Load Balancer.

8. Connect to Webserver on port 80 or 443.

9. Web server receives the GET request.

10. Web Application talks to Database

11. Your Browser renders the HTML into a viewable website.
