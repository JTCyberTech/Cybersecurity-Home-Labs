# How websites work

- Your browser (e.g., Safari, Google Chrome) requests information from a web server when you visit a website.
- The web server is a dedicated computer located elsewhere that handles your requests.
- The server responds with data that your browser uses to display the webpage.

<p align="center">
<br/>
<img src="https://i.imgur.com/ezQZN17.png" height="90%" width="90%" alt=""/>
<br />

There are two major components that make up a website:

- Front End (Client-Side) - the way your browser renders a website.
- Back End (Server-Side) - a server that processes your request and returns a response.

<h2></h2>

<h2>Questions</h2>

1: What term best describes the component of a web application rendered by your browser?

`Front End`


<h2></h2>

# HTML

Websites are primarily created using:

- HTML is used to build websites and define their structure.
- CSS is employed to enhance the visual appeal of websites by adding styling options.
- JavaScript is essential for implementing complex features on web pages through interactivity.


HTML (HyperText Markup Language) is the foundation of websites. Elements, also called tags, are the basic components of HTML. Elements instruct the browser on how to display content. The structure of a basic HTML document is consistent across websites.

<p align="center">
<br/>
<img src="https://i.imgur.com/S5HXRjK.png" height="90%" width="90%" alt=""/>
<br />

- The <!DOCTYPE html> defines that the page is a HTML5 document. This helps with standardisation across different browsers and tells the browser to use HTML5 to interpret the page.
- The <html> element is the root element of the HTML page - all other elements come after this element.
- The <head> element contains information about the page (such as the page title)
- The <body> element defines the HTML document's body; only content inside of the body is shown in the browser.
- The <h1> element defines a large heading
- The <p> element defines a paragraph
- There are many other elements (tags) used for different purposes. For example, there are tags for buttons (<button>), images (<img>), lists, and much more.

<h2></h2>

- Tags can contain attributes like the class attribute for styling elements, e.g., <p class="bold-text">.
- The src attribute is used in images to specify the image's location, e.g., <img src="img/cat.jpg">.
- Elements can have multiple attributes, each serving a unique purpose, e.g., <p attribute1="value1" attribute2="value2">.

<h2></h2>

- Elements can have an "id" attribute (e.g., <p id="example">).
- The "id" attribute is unique to the element.
- Unlike the "class" attribute, multiple elements can't share the same "id."
- "id" attributes are used for unique identification and styling.
- JavaScript can also use "id" attributes to target specific elements.

<h2></h2>

# JavaScript

- JavaScript (JS) is a widely popular programming language for creating interactive web pages.
- HTML is used for structuring web content, while JavaScript controls web page functionality.
- Without JavaScript, web pages would lack interactivity and remain static.
- JS enables real-time updates to web pages, such as changing button styles on user interactions.
- It can be used to create dynamic animations and respond to events on web pages.

<h2></h2>

- JavaScript can be added to web pages within <script> tags or included remotely using the src attribute.
- You can use JavaScript to find HTML elements and manipulate their content, like changing text.
- HTML elements can trigger JavaScript actions through events like "onclick" or "onhover."
- You can define event actions both directly in HTML elements and within JavaScript script tags.


<h2></h2>

# Sensitive Data Exposure

- Sensitive Data Exposure: Occurs when a website fails to protect or remove sensitive clear-text information in its frontend source code.
- Website Vulnerability: Sensitive data is often exposed in HTML or JavaScript elements, making it accessible to anyone viewing the page source.
- Risk of Unauthorized Access: Attackers can leverage this information to gain unauthorized access to various parts of the web application.
- Examples: Temporary login credentials in HTML comments can be exploited to log in or access backend components.
- Security Assessment: Reviewing the page source code is a crucial step in assessing web application security to identify exposed login credentials or hidden links.


<h2></h2>

# HTML Injection

- HTML Injection is a vulnerability caused by displaying unfiltered user input on a webpage.
- Failing to sanitize user input can allow attackers to inject malicious HTML code into a vulnerable website.
- Input sanitization is crucial for website security, as user input is often used in both frontend and backend functionality.
- HTML injection is a client-side vulnerability, while other vulnerabilities like database injection manipulate database queries.
- Users with control over input can submit HTML or JavaScript code, enabling them to control a webpage's appearance and functionality.

<h2></h2>

- User input in a form can be passed to a JavaScript function and output to a web page.
- If users input their own HTML or JavaScript code, it will be executed by the JavaScript function, potentially causing security issues.
- It's essential never to trust user input and sanitize it to prevent malicious input.
- Sanitizing input in this context would involve removing HTML tags to enhance security.
