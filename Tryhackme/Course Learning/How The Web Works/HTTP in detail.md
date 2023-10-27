# What is HTTP(S)?

HTTP (HyperText Transfer Protocol):

- Developed by Tim Berners-Lee and team between 1989-1991.
- Used for transmitting webpage data, including HTML, images, videos, etc.
- Standard protocol for communication with web servers.

HTTPS (HyperText Transfer Protocol Secure):

- Secure version of HTTP.
- Encrypts data to protect it from unauthorized access.
- Provides assurance that you're connecting to the genuine web server, preventing impersonation.

<h2></h2>

<h2>Questions</h2>

1. What does HTTP stand for?

`Hyper Text Transfer Protocol`

2. What does the S in HTTPS Stand for?

`Secure`

3. On the mock webpage on the right there is an issue, once you've found it, click on it. What is the challenge flag?

`THM{INVALID_HTTP_CERT}`


<h2></h2>

# Requests And Responses

- Website access involves your browser making requests to a web server for assets like HTML and images.
- To access these resources, you must specify the location and method, which is done through URLs (Uniform Resource Locators).

<h2></h2>
  
<h3>What is a URL? (Uniform Resource Locator)</h3>

- URL (Uniform Resource Locator) is a common term if you've used the internet.
- A URL serves as an instruction for accessing online resources.
- URLs come in various formats, and not all features are used in every request.

<p align="center">
<br/>
<img src="https://i.imgur.com/yp88Wqp.png" height="90%" width="90%" alt=""/>
<br />

- Scheme: This instructs on what protocol to use for accessing the resource such as HTTP, HTTPS, FTP (File Transfer Protocol).

- User: Some services require authentication to log in, you can put a username and password into the URL to log in.

- Host: The domain name or IP address of the server you wish to access.

- Port: The Port that you are going to connect to, usually 80 for HTTP and 443 for HTTPS, but this can be hosted on any port between 1 - 65535.

- Path: The file name or location of the resource you are trying to access.

- Query String: Extra bits of information that can be sent to the requested path. For example, /blog?id=1 would tell the blog path that you wish to receive the blog article with the id of 1.

- Fragment: This is a reference to a location on the actual page requested. This is commonly used for pages with long content and can have a certain part of the page directly linked to it, so it is viewable to the user as soon as they access the page.

<h2></h2>

<h3>Making a Request</h3>

<p align="center">
<br/>
<img src="https://i.imgur.com/h3csKLQ.png" height="90%" width="90%" alt=""/>
<br />
It's possible to make a request to a web server with just one line "GET / HTTP/1.1"

- A richer web experience requires sending additional data beyond just the basic request.
- This additional data is sent in the form of "headers."
- Headers contain extra information that is provided to the web server during communication.
- More details about headers will be covered in the Header task.

<p align="center">
<br/>
<img src="https://i.imgur.com/v6KkamR.png" height="90%" width="90%" alt=""/>
<br />

<p align="center">
<br/>
<img src="https://i.imgur.com/14F7IFz.png" height="90%" width="90%" alt=""/>
<br />


<h2></h2>

<h2>Questions</h2>

1. What HTTP protocol is being used in the above example?

`HTTP/1.1`

2. What response header tells the browser how much data to expect?

`Content-Length`

<h2></h2>

# HTTP Methods

HTTP methods indicate the client's intended action in an HTTP request.Common HTTP methods include GET and POST.

- GET Request: This is used for getting information from a web server.
- POST Request: This is used for submitting data to the web server and potentially creating new records.
- PUT Request: This is used for submitting data to a web server to update information.
- DELETE Request: This is used for deleting information/records from a web server.

<h2></h2>

<h2>Questions</h2>

1. What method would be used to create a new user account?

`POST`

2. What method would be used to update your email address?

`PUT`

3. What method would be used to remove a picture you've uploaded to your account?

`DELETE`

4. What method would be used to view a news article?

`GET`


<H2></H2>

# HTTP Methods

<h3>HTTP Status Codes:</h3>

- HTTP server responses always begin with a status code in the first line.
- Status codes inform the client about the outcome of their request.
- Status codes are categorized into 5 different ranges.

<p align="center">
<br/>
<img src="https://i.imgur.com/JXxBpuo.png" height="90%" width="90%" alt=""/>
<br />

- 100-199 - Information Response: Some status codes signal the client to continue sending their request after the initial part is accepted, but these codes are rarely used today.
- 200-299 - Success: These status codes indicate that the client's request was successful.
- 300-399 - Redirection: Status codes are used to redirect the client's request to another resource, which can be a different webpage or even a different website.
- 400-499 - Client Errors: A status code tells the client if there was an error in their request.
- 500-599 - Server Errors: This is for server errors, which typically mean a big issue with the server's request handling.

<h2></h2>

<h3>Common HTTP Status Codes:</h3>

- HTTP status codes play a crucial role in communication between web clients and servers.
- Numerous HTTP status codes exist, covering a wide range of scenarios and responses.
- Applications can even define their custom HTTP status codes to suit their specific needs.
- This discussion will focus on the most common and widely encountered HTTP responses.

<p align="center">
<br/>
<img src="https://i.imgur.com/UFTFjCc.png" height="90%" width="90%" alt=""/>
<br />

- 200 - OK: The request was completed successfully.
- 201 - Created: A resource has been created (for example a new user or new blog post).
- 301 - Moved Permanently: This tells the client's browser to go to a new webpage or informs search engines that the page has moved to a different location.
- 302 - Found: Similar to a permanent redirect, but temporary and subject to change.
- 400 - Bad Request: The status code informs the browser if there's an issue with the request, like missing or incorrect parameters.
- 401 - Not Authorised: You can't access this resource until you log in with a username and password.
- 403 - Forbidden: You can't access this content, even if you're logged in.
- 404 - Page Not Found: The page/resource you requested does not exist.
- 405 - Method Not Allowed: If you send the wrong type of request to a resource (e.g., a GET request when it expects a POST request), you'll get an error message.
- 500 - Internal Service Error: The server doesn't know how to handle an error with your request.
- 503 - Service Unavailable: The server can't process your request because it's either too busy or undergoing maintenance.

<h2></h2>

<h2>Questions</h2>

1. What response code might you receive if you've created a new user or blog post article?

`201`

2. What response code might you receive if you've tried to access a page that doesn't exist?

`404`

3. What response code might you receive if you've tried to access a page that doesn't exist?

`503`

4. What response code might you receive if you try to edit your profile without logging in first?

`401`

<h2></h2>

# Headers

- Headers in HTTP requests are used to send additional data to the web server.
- While no headers are strictly required for making an HTTP request, they are essential for viewing a website properly.

<h2></h2>

<h3>Common Request Headers</h3>

﻿These are headers that are sent from the client (usually your browser) to the server.

- Host: Specifies the desired website when the server hosts multiple sites.
- User-Agent: Informs the server about your browser for proper website formatting and compatibility.
- Content-Length: Indicates the amount of data in a web request, preventing data loss.
- Accept-Encoding: Communicates supported compression methods for efficient data transmission.
- Cookie: Data sent to the server to help remember your information (see cookies task for more information).

<h2></h2>

<h3>Common Response Headers</h3>

These are the headers that are returned to the client from the server after a request.

- Set-Cookie: Stores information sent back to the web server on each request, related to cookies.
- Cache-Control: Specifies how long to keep response content in the browser's cache before requesting it again.
- Content-Type: Informs the client about the type of data being returned (e.g., HTML, CSS, JavaScript, Images, PDF, Video), enabling proper data processing.
- Content-Encoding: Describes the compression method used to reduce data size when transmitting it over the internet.

<h2></h2>

<h2>Questions</h2>

1. What header tells the web server what browser is being used?

`User-Agent`

2. What header tells the browser what type of data is being returned?

`Content-Type`

3. What header tells the web server which website is being requested?

`Host`

<h2></h2>


# Cookies

- Cookies are small pieces of data stored on your computer.
- They are set by web servers using a "Set-Cookie" header and sent back with subsequent requests.
- Cookies help maintain your identity, personal settings, and site visit history, compensating for HTTP's statelessness.

<p align="center">
<br/>
<img src="https://i.imgur.com/YwCqJdy.png" height="90%" width="90%" alt=""/>
<br />

- Cookies serve various purposes, with website authentication being a common use.
- Cookie values typically contain tokens, not clear-text passwords.
- Tokens are unique secret codes designed to be difficult for humans to guess.

<h2></h2>

<h3>Viewing Your Cookies</h3>

- Use developer tools in your browser to view sent cookies to a website.
- Access developer tools by clicking the "View Site" button for a guide.
- In developer tools, go to the "Network" tab to see requested resources.
- Click on each resource for a detailed request and response breakdown.
- Find sent cookies in the "Cookies" tab of the request.

<h2></h2>

<h2>Questions</h2>

1. Which header is used to save cookies to your computer?

`Set-Cookie`
