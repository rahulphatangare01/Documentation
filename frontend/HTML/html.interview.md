# HTML Interview Questions

## HTML Basic Interview Questions

<details>
<summary>
1.<b>  What does HTML stand for and what is its purpose?</b>
</summary>

**HTML** or `Hyper Text Markup Language` is the standard language for creating web pages and applications. HTML5, the latest version as of 2022, introduces several new elements and attributes, elevating user experience and software application standards.

HTML is responsible for structuring web content, ensuring accessibility, and guiding how web pages are visually presented. It remains the foundational structure for running nearly all web content.

**Core Functionalities**

1. **Structuring Content**: Tags like `<header>`, `<footer>`, and `<section>` divide content, streamlining its organization.
2. **Embedding Media**: HTML provides tags to incorporate multimedia such as images, audio, and video.
3. **Form Handling**: Interactive sections such as user input forms are defined with input and label tags.
4. **Hyperlinks**: Essential for navigation, hypertext links like `<a>` anchor content within or outside the webpage.
   **Accessibility Features**: Semantic tags like `<nav>` and <article> not only structure data but also improve accessibility for users relying on screen readers.
   **Integration of Other Technologies**: Can integrate with scripting languages like JavaScript and libraries and frameworks like Bootstrap for enhanced visual appeal.

**Compatibility and Development**

The primary objective of HTML5 is to improve the language's support for the latest multimedia, while keeping it easily readable by humans. It was designed to be backward and forward compatible, so that content written in previous versions can be seamlessly integrated and interact with content authored in subsequent versions.

**Visual Presentation and User Interface Adaptations**
HTML5 is engineered to provide more flexibility, control, and aesthetic maturity for web pages and web-based software applications. Web developers can use it to craft modern web interfaces with rich visual and multimedia experiences. It also allows for more responsive and adaptive design, ensuring optimal viewing on a variety of devices and screen sizes. This reflects a broader shift in technology toward a more device-agnostic user experience.

**The Role of CSS and JavaScript**
While HTML offers static content, CSS and JavaScript enable additional layers of styling, interactivity, and dynamic content updates. The integration of these three technologies (referred to as HTML-CSS-JS) stands as the trio that forms the backbone of almost all web-based content. They're often presented as HTML5-CSS3-JS to signify unified modern best practices. Online, there's even tools that combine these technologies into a single framework or language such as WebAssembly or Dart. The trio represents a more modular approach, allowing distinct teams to focus on individual layers, streamlining development in larger projects. Mastering their intersection helps in designing a robust and cohesive user experience. This concept is captured by the acronym "PEA", which stands for the Platform (HTML), the Engine (JavaScript), and the Appearance (CSS). Each category focuses on a distinct aspect of user experience.

**Practical Uses**

**Website Development**: All traditional web resources, from simple blogs to expansive e-commerce sites, remain based primarily on HTML.
**Web Applications**: Web technologies have evolved significantly, allowing for sophisticated applications like Google Docs, Trello, and Slack to run entirely in a web browser. HTML5 has played a pivotal role in this development.
**Advertising & Media**: HTML5's advanced media handling tools have made it the standard for online ads and multimedia content.

</details>

<details>
<summary>
2.<b>   What is a meta tag?</b>
</summary>

A `meta tag` provides metadata about a web page. The page information is not displayed on the web page.
but is used by browsers and search engines to understand and categorize the content of the page such as page description, keywords, author, and viewport settings for responsive design.

```jsx harmony
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8"> //Special characters to use like ASCII (American Standard Code for Information Interchange) The ASCII code for uppercase 'A' is 65.The ASCII code for lowercase 'a' is 97.The ASCII code for the digit '0' is 48.
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="This is food description">
    <meta name="keyword" content="food, food service, food industry">
    <meta name="robots" content="index, follow">
    <meta name="author" content="Nandakishore">
    <link rel="stylesheet" href="assets/style.css">
    <title>Food4You</title>
</head>
<body>
</body>
</html>

```

</details>

<details>
<summary>
3.<b> Difference between link and anchor tag?</b>
</summary>

- `Link` tag It is used for linking the external resources file.
- `Anchor` tag It is used for linking to navigate one web page to another web page and these links are clickable.
</details>

<details>
<summary>
4.<b> .What are the new input types in HTML5?</b>
</summary>

New input types offered by `HTML5`

- type=”week”
- type=”month”
- type=”time”
- type=”datetime”
- type=”datetime-local”
- type=”color”
- type=”search”
- type=”range”
- type=”url”

</details>

<details>
<summary>
5.<b>  What are the different types of lists in HTML?</b>
</summary>

**There are 3 types of lists:**

- **Ordered list** It's used when you want to display a list of items and each item is marked with a number.
- **Unordered list** On the other hand an unordered list displays a list of items and each item is marked with a bullet point.
- **Definition list** each list item with a title and a description.

```jsx harmony
<ol type="I">
        <li>Apple</li>
        <li>Banana</li>
        <li>Carrot</li>
</ol>
<ul type="circle">
        <li>Apple</li>
        <li>Banana</li>
        <li>Carrot</li>
</ul>
```

</details>

<details>
<summary>
6.<b>  What is a marquee in HTML?</b>
</summary>

A` marquee tag` is used to make text or images scroll automatically on a web page. However, it's no longer in modern (HTML5)

</details>

<details>
<summary>
7.<b> What is the difference between HTML and CSS?</b>
</summary>

HTML is used to display the content on a web page, while CSS is used to control the presentation, layout, and design of a web page.

</details>

<details>
<summary>
8.<b> How many ways to write css in HTML?</b>
</summary>
There are three ways to write CSS in HTML documents:

- Inline
- Internal
- External
</details>

<details>
<summary>
9.<b> What is dom in HTML?</b>
</summary>
DOM stands for Document Object Model. When a web page is getting loaded that time the browser creates a dom of the page and it is constructed as a tree of objects.
</details>

<details>
<summary>
10.<b> What are the various formatting tags in HTML5?</b>
</summary>

```jsx harmony
<sup></sup> //Superscript
<sub></sub> //Subscript
<del></del> //strikethrough
<strong></strong> //Bold
<em></em> //Italic or emphasized
```

</details>

<details>
<summary>
11.<b> What are the root tags in html?</b>
</summary>

There are some root tags. Without including these root tags in HTML we can’t create web pages.

- html
- head
- body
</details>

<details>
<summary>
12.<b> What is the difference between an ID and a class in HTML?</b>
</summary>

An ID is used to identify a unique element on a web page, while a class is used to identify a group of elements.

</details>

<details>
<summary>
13.<b> What is the purpose of the href attribute in the tag?</b>
</summary>

href attribute is used to specify the URL of the hyperlink.It tells the browser where to navigate when the link is clicked.URL(Uniform Resource Locator)

</details>

<details>
<summary>
14.<b> .What is the purpose of the src attribute in the  tag?</b>
</summary>

src attribute specifies the source file path.

</details>

<details>
<summary>
15.<b> What are some new tags introduced in HTML5?</b>
</summary>

Some new tags in HTML5 include:

- header
- footer
- section
- nav
- article
- main
- aside
- video
- audio
</details>

<details>
<summary>
16.<b> Why we use semantic tags?</b>
</summary>

For deveveloper easier to read and understand as well as It help the search engines.

</details>

<details>
<summary>
17.<b> What are the attributes in html?</b>
</summary>

Attributes are special words used inside the opening tag to control the element's behaviour

- style
- href
- src
- alt
- class
- Id
- type
- value
- width
- height
</details>

<details>
<summary>
18.<b> .What is the difference between inline, block-level and inline-block elements?</b>
</summary>

- `Inline elements` doesn’t start with a new line and only take up as much width as necessary.
- `Block-level elements` always start with a new line and take up full width.
- `inline-block` It’s formatted just like the inline element, where it doesn’t start on a new line. but, you can set width and height values.
</details>

<details>
<summary>
19.<b> What is the use of an iframe tag?</b>
</summary>

iframe stands for "inline frame tag." It's used to embed content from another source directly into the current webpage.
To integrate external resources like web pages, videos, maps, and more into your own page.

```jsx harmony
<iframe src="https://www.bing.com/" frameborder="0" width="800"></iframe>
```

</details>

<details>
<summary>
20.<b> What is the difference between HTML and XHTML?</b>
</summary>

HTML and XHTML Both essential languages for creating web pages.The main difference between them syntax and structure.

| HTML                                           | XHTML                                           |
| ---------------------------------------------- | ----------------------------------------------- |
| HTML is Hypertext Markup Language              | XHTML is Extensible Hypertext Markup Language   |
| It is not a case-sensitive language            | It is a case-sensitive language                 |
| It is An application of SGML                   | It is An application of XML                     |
| It Can function properly without a closing tag | It Can’t function properly without being closed |
| It No hard rule on structures of the elements  | It Structure of the elements should be followed |
| It Attributes have quotes as optional          | It Attributes have quotes mandatory             |

</details>

<details>
<summary>
21.<b> Different between html4 and html5?</b>
</summary>

1. **Doctype Declaration**:

- HTML 4 we have to declare a little lengthy code of doctype.
- HTML 5 we have to declare in short code of doctype

2. **Semantic Elements**:

- HTML 4 we need to specify a name for the div element.
- HTML 5 Introduces semantic elements like section, article, nav, header, footer, etc., which provides a more meaningful way to structure content.

3. **Multimedia Support**:

- HTML 4 Relying on third-party plugins like Flash for multimedia content.
- HTML 5 Introduces native support for multimedia with audio and video tags, reducing the need for third-party plugins.

4. **Input Types**:

- HTML4: Limited input types available like text, password, email, number, checkbox, radio, submit, reset, hidden.
- HTML5: Introduces new input types like week, month, time, datetime, datetime-local, color etc.

</details>

<details>
<summary>
22.<b> what is the difference between http and https?</b>
</summary>

The main difference between these two terms `http` and `https`.

**HTTP** `(Hypertext Transfer Protocol)`:

- HTTP is a protocol used for transferring data over the internet.
- It is not secure because the data transferred between the client and website is not encrypted
- HTTP is fast compared to HTTPS

**HTTPS** `(Hypertext Transfer Protocol Secure)`:

- HTTPS is a secure version of HTTP.
- It uses SSL (Secure Sockets Layer) protocols to encrypt the data transmitted between the client and website.
- This encryption helps protect sensitive information like passwords, credit card numbers, and personal details from being intercepted.
- HTTPS It helps to improve search rankings

</details>

<details>
<summary>
23.<b> What are the Inline and Block-level tags?</b>
</summary>

| Inline tags | Block-level tags |
| ----------- | ---------------- |
| a           | header           |
| strong      | footer           |
| em          | section          |
| img         | form             |
| button      | h1 to h6         |
| input       | hr               |
| br          | p                |
| label       | ol               |
| span        | ul               |
| sub         | li               |
| sup         | dl               |
| textarea    | dt               |
| script      | dd               |
| small       | table            |
|             | div              |
|             | nav              |
|             | aside            |
|             | video            |

</details>

<details>
<summary>
24.<b>  What is the use of the target attribute in the tag?</b>
</summary>

- \_blank: It opens the link in a new window.
- \_self: It opens in the same window.
</details>

<details>
<summary>
25.<b> What are HTML Entities?</b>
</summary>

`HTML` Entities are special characters used to represent characters that cannot be typed on a keyboard

- < for <(less than)
- > for <(greater than)
- © for <(copyright right)
- ® for (Register)
- ™ for (Trade Mark)
</details>

<details>
<summary>
26.<b> What is a manifest file in HTML5?</b>
</summary>

A Manifest file is a simple text file that tells the browser what to cache and what not to cache. In offline and online mode.

**There are three sections of a Manifest file:**

- **CACHE** - Files listed here are cached after they are downloaded for the first time.
- **NETWORK** - Files listed here require a connection to the server, and are never cached.
- **FALLBACK** - Files listed here specify fallback pages if a page is inaccessible.

</details>

<details>
<summary>
27.<b> Explain the concept of web storage in HTML5?</b>
</summary>

- web applications can store data locally within the client browser.
- Before HTML5 version, application data had to be stored in cookies.
- Web storage is more secure, and large amounts of data can be stored locally, without affecting website performance.

**There 2 object** :-

**LocalStorage**- for multiple sessions with no expired date.
**sessionStorage**- for single session(data is lost when browser is tab closed).

Example:-

- windows.localstorage.setItem(key,value);
- value=windows.localstorage.getItem(key);
- windows.localstorage.removeItem(key)
- windows.sessionstorage.setItem(key,value);
- value=windows.sessionstorage.getItem(key);
- windows.sessionstorage.removeItem(key

</details>

<details>
<summary>
28.<b> What is cookies and how it works?</b>
</summary>

A cookie is a small piece of data created by a web server on browser to remember information about the user and tracking user behaviour.
Generally, email and password are will not store directly in cookies, instead of that server will create a session ID for session management.

</details>

<details>
<summary>
29.<b> Explain Different between image and figure tag?</b>
</summary>

Both tags are used to display image on a webpage, but they have different purposes.

- An image tag is use to display on a webpage. It is a self-closing tag. Requires the "src" attribute to specify image source. Optional attributes like "alt," "width," and "height" can be included.
- The figure tag is used to group together an image or a video along with a caption. It Requires a closing tag. It is used to semantically organize the content.
</details>

<details>
<summary>
30.<b> How to add favicon in website?</b>
</summary>

To add a favicon to a website in between head tag use the link tag inside of link tag we have some attribute rel for icon type is format href for source for image.

```jsx harmony
<link rel="icon" type="image/x-icon" href="/images/favicon.ico">

```

</details>

<details>
<summary>
31.<b> Different between div and span?</b>
</summary>

A div element is used for block-level organize and styling of page, where as a span element is used for inline organize and styling.

</details>

<details>
<summary>
32.<b> How many types of links in html?</b>
</summary>

It has 5 types of links:

```jsx harmony

<a href="https://www.example.com">Visit Example Website</a> // External link

<a href="https://www.example.com">
  <img src="image.jpg" alt="Example Image"> //Image link
</a>

<a href="mailto:info@example.com">Send Email</a> //Email link

<a href="#section2">Bookmark Section 2</a> //Bookmark link
<div id="section2">This is Section 2</div>

<a href="tel:+1234567890">Call Us</a> //Phone link
```

</details>

<details>
<summary>
33.<b> .What is Bookmark link?</b>
</summary>

A bookmark link is used to navigate to a specific section on the same website.

```jsx harmony
  <body>
      <a href="#home">Home</a>
      <a href="#about">About</a>

      <section id="home">
        <h2>Section Home</h2>
        <p>This is home page</p>
      </section>

       <a href="#home">Home</a>
      <section id="about">
        <h2>Section Home</h2>
        <p>This is home page</p>
      </section>
  <body/>
```

</details>

<details>
<summary>
34.<b> What is the purpose of base tag?</b>
</summary>

The base tag is used for common base url for all relative urls within a document and this tag is placed in head tag.

```jsx harmony
 <!DOCTYPE html>
<html>
  <head>
    <title>Hello, World!</title>
    <link rel="stylesheet" href="styles.css" />
    <base href="https://www.abc.com/" />
  </head>
  <body>
      <a href="page1.html">Home</a>
      <a href="page2.html">About</a>
  </body>
</html>
```

</details>

<details>
<summary>
35.<b> What are table, tr, th, td elemetns and advantesges & desiadvantages?</b>
</summary>

- Table is the container for the entire table.
- Tr (table row) is used to define a row in the table.
- Th (table header) is used to represent the column headers names.
- Td (table data) is used to represents the regular cells in a table.
- Table structure is not good for mobile device(not responsive).

```jsx harmony
<table border="1" cellpadding="10" cellspacing="0" width="100%">
  <thead>
    <tr>
      <th colspan="2">S.No</th>
      <th>Name</th>
      <th>Email</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td rowspan="2">1</td>
      <td>Nandakishore</td>
      <td>nandakishore695@gmail.com</td>
      <td>7893797371</td>
    </tr>
    <tr>
      <td>Akshay</td>
      <td>akshay@gmail.com</td>
      <td>7893797371</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td colspan="3">Total</td>
      <td>20</td>
    </tr>
  </tfoot>
</table>
```

</details>

<details>
<summary>
36.<b> What is the colspan and rowspan attribute in html?</b>
</summary>

- The colspan attribute is used to merge multiple cells in horizontally into a single cell.
- The rowspan attribute is used to merge multiple cells in vertically into a single cell.
- Colspan and rospan attribute is applicable to th and td tag only.
</details>

<details>

## HTML Advance Interview Questions

<summary>
37.<b> Describe the basic structure of an HTML document.</b>
</summary>

**HyperText Markup Language** (`HTML`) serves as the backbone of web content, defining its structure and semantics. We will now walk you through the fundamental elements of an HTML document.

**Basic Structure of an HTML Document**
An HTML document consists of two primary sections: the head and the body.

**Document Type Declaration (DOCTYPE)**
The Document Type Declaration (DOCTYPE) is not an HTML tag; it's an instruction to the web browser about what version of HTML the page is written in.

```jsx harmony
<!DOCTYPE html>
```

This declaration shows that the document is an HTML5 document.

**HTML Element**
The `html` element is the root element of an HTML page. It encompasses the entire content, both head and body.

```jsx harmony
<html>
    <!-- Head and Body Sections Are Nested Inside -->
</html>
```

**Head Section**
The `head` section provides meta-information about the document. It isn't displayed in the web browser itself but serves various other purposes, from providing a title to linking external resources.

```jsx harmony

<head>
    <!-- Title and Meta-Tags, Styles, Scripts, etc. -->
</head>
```

**Title Element**
The `title` element specifies the document's title, which is displayed in the browser's title bar or tab.

```jsx harmony
<title>Your Page Title</title>
```

**Body Section**
The body section encapsulates the document's visible content—what users see and interact with.

```jsx harmony
<body>
    <!-- Content Visible to Users: Headings, Paragraphs, Images, etc. -->
</body>
```

</details>

<details>
<summary>
38.<b>What do DOCTYPE and html lang attributes do? </b>
</summary>

**Document Type** (DOCTYPE) and the `lang` attribute play crucial roles in our webpages.

**DOCTYPE: Defining Document Type and Validation Mode**

**Purpose**

- Specifies the HTML or XHTML version used in the document.
- Identifies parsing method and algorithm for the web browser, affecting consistency.

**Code Example**
The `<!DOCTYPE>` declaration is placed at the very top of the HTML file, even before the <html> tag begins.

```jsx harmony

<!DOCTYPE html>
<html>
  <head>
    <title>Page Title</title>
  </head>
  <body>
    <!-- Content -->
  </body>
</html>
```

**Lang Attribute: Language Specification**
The `lang` attribute, present in the HTML tag, specifies the primary language used in the document. Its value is a primary language subtag as defined in RFC 5646 (BCP 47) and it can include a valid language code, a valid language code followed by a valid region code, or simply "und" for unspecified language.

Code Example

```jsx harmony
<!DOCTYPE html>
<html lang="en-US">
  <head>
    <title>Page Title</title>
  </head>
  <body>
    <h1>Welcome</h1>
    <p>This is a demo page.</p>
  </body>
</html>
```

</details>

<details>
<summary>
39.<b> What is the difference between head and body tags?</b>
</summary>

While the `<head>` and `<body>` tags are fundamental to every HTML document, they serve distinct purposes and are located in separate areas of the web page.

**Key Distinctions**

1. **Role and Content**
   **Head**: Houses meta-information, such as document title, character encoding, and stylesheets, all of which are essential for page setup but not visible to the user.
   **Body**: Contains the bulk of visible content, including text, images, videos, links, and more.
2. **Placement in the HTML File**
   **Head**: Precedes the body and provides setup before actual content is rendered.
   \_ : Follows the head section and encompasses all visible content.
3. **Common Elements in Each Section**
   **Head**: Typically links to CSS files or may have inline CSS, contains the document title, any JavaScript reference, character set declaration, and meta tags.
   **Body**: Holds structural components like headers, navbars, articles, sections, and the footer, along with visual content like images and visible text.

**Visual Representation in the HTML File**

1.  **<head> Section**:

```jsx harmony
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <link rel="stylesheet" type="text/css" href="styles.css">
  </head>
  <body>
    <!-- Content Here -->
  </body>
</html>
```

2. **<body> Section**:

```jsx harmony
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <link rel="stylesheet" type="text/css" href="styles.css">
  </head>
  <body>
    <header>
      <h1>Welcome!</h1>
      <nav>
        <ul>
          <li><a href="#">Home</a></li>
          <li><a href="#">About</a></li>
          <li><a href="#">Contact</a></li>
        </ul>
      </nav>
    </header>

    <section>
      <h2>Recent Posts</h2>
      <article>
        <h3>Post Title</h3>
        <p>Post content goes here.</p>
      </article>
    </section>

    <footer>
      <p>&copy; 2023 MySite</p>
    </footer>

  </body>
</html>
```

</details>

<details>
<summary>
40.<b> Can you explain the purpose of meta tags in HTML?</b>
</summary>

**Meta tags** provide metadata about a web page through information invisible to visitors but essential for search engines, social media, and other web technology. This metadata includes details such as the page's title, keywords, and description.

**Key Meta Tags**
**Meta Description**: A concise summary of the page's content, often used in search engine results.

**Meta Keywords**: Historically used to specify relevant keywords for the page, but they have been largely deprecated due to abuse by spammers.

**Meta Robots**: Directs search engine bots on how to interact with the page, such as index it for search results, follow its links, or refrain from both.

**Meta Viewport**: Crucial for responsive design, it guides the browser on how to scale and display the page, especially useful for mobile devices.

**Meta Charset**: Defines the character encoding used on the webpage, ensuring text is displayed correctly.

**Meta Author**: Identifies the page's creator or author.

**Open Graph, Twitter Cards**: Specialized meta tags used by social platforms like Facebook and Twitter to optimize page sharing.

**Canonical URL**: Indicates the preferred URL when a page can be accessed through multiple paths.

**Refresh and Redirect**: Older, less common meta tags that dictate page behavior.

**Code Example: Common Meta Tags**
Here is the HTML code:

```jsx harmony
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="description" content="This is a sample web page with a concise description.">
    <meta name="keywords" content="HTML, meta tags, web design, SEO">
    <meta name="author" content="John Doe">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sample Web Page</title>
</head>
<body>
    <!-- Page content goes here -->
</body>
</html>
```

**Responsible Use of Meta Tags**
With search engines evolving, many tags have diminished in significance. Here's the current state:

**Still Relevant**: Meta Description, Viewport, Charset, Author, and Canonical
**Limited Effect**: Keywords, Refresh, and Robots
**Specialized Fields**: Open Graph, Twitter Cards are necessary for tailored content on social platforms

To maintain a robust online presence, focus on high-quality content, user experience, and technical soundness, and don't solely rely on meta tags.

</details>

<details>
<summary>
41.<b> How do you link a CSS file to an HTML document?</b>
</summary>

Linking a CSS file to an HTML document is a fundamental step for styling. This is generally done by indicating the CSS file's path in the `head` section of the HTML file using `<link>` tags.

**HTML Link Tag: <link>**
HTML uses the `<link>` tag to integrate external resources such as CSS files.

**Syntax**

```jsx harmony
<link rel="stylesheet" href="path/to/style.css">
```

**rel**: Specifies the type of relationship between the current document and the linked file. For CSS, it should be set to "stylesheet".

**href**: Points to the location of the external CSS file. This can be via an absolute URL (i.e., http://...) or a relative path to the HTML file.

**type**: Supplied for legacy purposes but is not required given the file is a CSS file.

**Code Example: Using the Link Tag**
Here is the HTML code:

```jsx harmony
<!DOCTYPE html>
<html lang="en">
<head>
    <link rel="stylesheet" href="path/to/style.css">
</head>
<body>
    <!-- Body content -->
</body>
</html>
```

</details>

<details>
<summary>
42.<b> How do you link a JavaScript file to an HTML document?</b>
</summary>

To link a JavaScript file to an HTML document, you need to use the `<script>` HTML tag. There are two primary ways to do this:

**External Script File**: Link a separate JavaScript file to your HTML document.
**Inline Script**: Embed JavaScript code directly within your HTML file.

**External Script File**
To use an external JavaScript file, follow these steps:

**Create the JavaScript File**: Save your JavaScript code in a separate file with a `.js` extension. For example, `script.js`.

**Link the JavaScript File to your HTML Document**: Add the following code within the `<head>` or at the end of the `<body>` section of your HTML file.

```jsx hrmony
<script src="path-to-your-js-file.js"></script>
```

Replace path-to-your-js-file.js with the actual path to your JavaScript file.

**Best Practices**
**Placement**: It's good practice to place your `<script>` tags at the end of the `<body>` section, just before the closing `</body>` tag. This ensures that the HTML content loads first, which can improve the website's initial rendering speed.

**Syntax**: The HTML5 specification does not require a closing tag for the `<script>` element.

**Inline Script**
You can also include JavaScript directly within your HTML file. This is called an "inline script." To do this, encase your JavaScript code within **<script>** tags, like this:

```jsx harmony
<script>// Your JavaScript code goes here</script>
```

**Best Practices**
**Content Separation**: For better code organization, it's often better to keep your JavaScript in a separate file, especially for larger applications.

**Caching**: When using an external JavaScript file, the browser caches the script, which can speed up your site on subsequent visits. However, if the script changes often, this caching can be a problem.

**Maintainability and Reusability**: Utilizing an external JavaScript file allows for better code management, reusability, and ease of making updates or fixes across multiple HTML files.

**Example HTML File**
Here is the code:

**Implementation: HTML File**

```jsx harmony
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="path-to-your-js-file.js"></script>
</head>
<body>
    <!-- Your content here -->
    <script>
        // Inline JavaScript code here.
    </script>
</body>
</html>
```

</details>

<details>
<summary>
43.<b> How do you add a comment in HTML and why would you use them?</b>
</summary>

To add a comment in HTML, wrap it between `<!-- and -->`.

For example:

```jsx harmony
<!-- This is a comment -->
<p>Hello, World!</p>
```

**Role of Comments in Development**
Comments ensure clear code comprehension and can be used for:

**Instructions**: Guiding developers on next steps.
**Documentation**: Articulating intricate code segments.
**Debugging**: Temporarily removing portions for bug testing.
**Reminders**: Highlighting sections for later revision.

**Best Practices for Using Comments**

**Purposeful Clarity**: Comments must explain what the code does, not how. Code and inline comments should clarify how the code works.
**Relevance**: Avoid stating the obvious and focus on unique or complex components.
**Conciseness**: Keep comments brief to reduce visual clutter.
**Regular Maintenance**: Update or remove outdated comments to maintain accuracy.

**When are Comments Unnecessary?**

- **Trivial Cases**: Comments like "
  wrapper" or "
  tag" denote the obvious.

- **Self-Explanatory Code**: Writing self-descriptive code eliminates the need for specific comments.

</details>

<details>
<summary>
44.<b> How do you serve your page in multiple languages?</b>
</summary>

Let's discuss the best practices for serving web pages in multiple languages and the corresponding HTML5 tag, `<html lang="en">`.

**Language Tag**
For serving content in multiple languages and optimizing accessibility and search engine performance, you should use the `lang` attribute on the `<html>` tag. This is considered a best practice, even if the page is only in English.

```jsx harmony
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Your Website</title>
  </head>
  <body>
    <!-- Page content here -->
  </body>
</html>
```

**Common Language Codes**

Most languages follow the two-letter ISO 639-1 code, such as "en" for English or "es" for Spanish. Some languages also use an extended ISO 639-2 or 639-3 code, which might require three to four letters, like "por" for Portuguese.

For dialects or region-specific content, you can use a hyphen, followed by an ISO 3166-1 alpha-2 country code. For instance:

- "en-GB" for British English
- "es-ES" for Spanish as spoken in Spain
- "pt-BR" for Brazilian Portuguese
- "pt-PT" for European Portuguese

  Understand that while the `lang` attribute assists in accessibility, user agents may not always recognize or act upon these subtags.

**SEO Considerations**
Serving content in multiple languages comes with SEO responsibilities. One common practice is to assign a language-specific URL for each version of your content. In addition to this, utilize human-readable URLs to effectively comminicate the language and the content topic/design.

For instance, use:

- `example.com/en-US/about` for pages in American English.
- `example.com/es-MX/sobre` for those in Mexican Spanish.

**AI-Clearance Required**
This technique requires further validation and clearance upon implementation as a lot is dependent on SEO constraints and localized content.

</details>

<details>
<summary>
45.<b> What are data-* attributes and when should they be used?</b>
</summary>

**Data attributes** in HTML5, often referred to as `data-\*` attributes, help embed custom data within HTML elements. This presents a powerful tool for web developers, facilitating streamlined `JavaScript` and `CSS` operations.

**Core Benefits**
**Accessibility**: Data attributes are easily accessible through the dataset API in JavaScript.

**Ignoring formatting tactics**: In places where content served by backend, cannot assume the content to always be JSON encoded, shortened, or have odd formatting.

**Data Isolation**: For better maintenance of web documents. Data attributes have clear, defined roles within HTML.

**Code Example: Using Data Attributes**
Here is the HTML & JavaScript:

```jsx harmony
<div id="user" data-name="John Doe" data-age="25"></div>

<script>
  const userDiv = document.getElementById('user');
  console.log(userDiv.dataset.name);  // Output: "John Doe"
  console.log(userDiv.dataset.age);   // Output: "25"
</script>
```

**Appropriate Use-Cases**
**Custom Content for DOM Elements**: For attaching extra information or configuration settings exclusively relevant to an HTML element.

**Example**: A div may have a data-show-tooltip attribute set to true to indicate it should display a tooltip.

**Interactivity Configuration**: When working with user-made widgets, data attributes can specify how they behave in a more structured, intended manner. Useful in contexts where individual DIV or section blocks have interactivity toggles, or categories.

**E-Commerce & Web Products**: To store product-specific IDs or additional details as they pertain to the DOM representation of a product in a catalog.

**Styling Signifiers**: You can leverage data attributes in CSS for different types of styling like category colors, hover effects, or even in JavaScript-based CSS declarations.

</details>

<details>
<summary>
46.<b> What is the difference between b and strong tags?</b>
</summary>

The `<b>` and `<strong>` tags are both used for text emphasis in HTML, but they have different semantic meanings.

**Bold vs. Strong**

- The purpose of the `<b>` tag is to make the text bold, mainly for visual styling.
- The `<strong>` tag, on the other hand, semantically emphasizes the text, indicating its importance.

**Semantic Importance**
The use of semantic tags like `<strong>` is beneficial for components like screen readers, browsers, and search engines, which can provide better user experience or understanding of content with proper emphasis.

**Code Example: B vs. Strong**
In the HTML, the content "Caution" is visually bold and the content "Urgent Notice!" is both visually bold and semantically strong.

```jsx harmony
<p>
  <b>Caution</b>: This action cannot be undone.
  <br>
  <strong>Urgent Notice!</strong> Please save your work before proceeding.
</p>
```

**General Best Practice**
**Visual Styling** is usually left to CSS. `<b>` should be used with caution, if at all, as it becomes redundant in many scenarios due to CSS's wide adoption.
Semantic Tags like `<strong>` provide context, clarity, and accessibility to the content.

</details>

<details>
<summary>
47.<b> When would you use em over i, and vice versa?</b>
</summary>

Let's see the difference between `'em'` and `'i'` HTML tags.

**When to Use 'em'**
The `'em'` tag italicizes the text by default and should be reserved for occasions when emphasis is needed.

One potential usage could be for interactive instructions:

```jsx harmony
<p>
  <strong>Press</strong> <em>Enter</em> to submit.
</p>
```

**When to Use 'i'**
The `'i'` tag, or italics tag, is often avoided for text styling. Instead, consider semantic HTML, CSS, or more explicit HTML options like `<em>` for emphasis, when possible.

Here's an example of `<em>` combined with CSS for an additional bit of fluorescence.

```jsx harmony
<p>
  His <em style="background-color: yellow; color: red;">anger</em> was palpable.
</p>
```

</details>

<details>
<summary>
48.<b> What is the purpose of small, s, and mark tags?</b>
</summary>

The `small`, `s`, and `mark` HTML5 tags are used to alter the structure and presentation of text content.

**<small>**
The `<small>` tag indicates that the enclosed text is of lesser importance, typically used for fine print, legal disclaimers, copyright notices, etc.

Here are examples:

**Use Case**

```jsx harmony
<footer>
  <small>&copy; 2022 Company Name</small>
</footer>
```

**`<s>`**
The `<s>` tag, which stands for "strike," is a non-semantic, obscure tag that is often replaced with a more meaningful tag, such as` <del>` for "deleted" content. However, it still visually strikes out its content.

**Use Case**

```jsx harmony
<p>
  Your discount code is: <s>EXPIRED123</s>
</p>
```

**Visual Representation**
Your discount code is: EXPIRED123

**`<mark>`**
The` <mark>` tag is used to **highlight** or set apart text without specifying any additional semantic information.

**Use Case**

```jsx harmony
<p>
  Important: Please <mark>schedule your appointment</mark> at least 48 hours in
  advance.
</p>
```

</details>

<details>
<summary>
49.<b> What are semantic HTML tags and why are they important?</b>
</summary>

**Semantic HTML** tags provide both structure and meaning to web content. They allow crawlers, browsers, and even assistive technologies to understand content better and present it more effectively. This approach improves accessibility and search engine optimization, making pages easier to maintain and understand.

**Benefits of Semantic Tags**

**SEO and Accessibility**: Employing semantic tags improves your page's search engine ranking and ensures it's accessible to all users, including those with disabilities.

**Consistent Structure**: Semantic tags establish a cohesive layout, vital for large websites or platforms.

**Relevance to Bots and Crawlers**: Search engine algorithms dissect web pages more accurately when content is correctly labeled.

**Content Division**: Segregating content by their meaning makes the document more understandable and maintainable.

**Common Semantic Tags**

- <p>: A paragraph.
- <h1> - <h6>: Headings, with 1 (highest) to 6 (lowest) levels.
- <ul> / <ol>: Unordered or ordered list.
- <li>: List item inside a list.
- <a>: Anchor, used for links.
- <img>: An image.
- <figure> / <figcaption>: For a figure such as an image, with accompanying caption.

**Necessary vs. Optional Tags**
While essential tags like `<header>` and `<footer>` indicate crucial sections, many are optional based on the website's nature or the page's segregation needs. For example, a blog may require the `<article>` tag, while a retail site might not.

In modern web development, the clear distinction offered by semantic tags is invaluable for quick comprehension and maintenance, yielding superior results for both users and developers.

**Code Example: Before vs. After Semantic HTML**
Consider the before and after examples to see the impact of semantic tags.

**Before Semantic HTML**

```jsx harmony
<div class="nav">
    <div class="logo">
        <a href="#">Logo</a>
    </div>
    <div class="nav-links">
        <a href="#">Home</a>
        <a href="#">About</a>
        <a href="#">Contact</a>
    </div>
</div>
<div class="main-wrapper">
    <div class="image">
        <img src="image.jpg" alt="A beautiful landscape">
    </div>
    <div class="content">
        <h3>Welcome</h3>
        <p>Some welcome text here.</p>
    </div>
</div>
<div class="footer">
    <p>© 2022 Company Name</p>
</div>
```

**After Implementing Semantic Tags**

```jsx harmony
<header>
    <div class="logo">
        <a href="#">Logo</a>
    </div>
    <nav>
        <a href="#">Home</a>
        <a href="#">About</a>
        <a href="#">Contact</a>
    </nav>
</header>

<main>
    <figure>
        <img src="image.jpg" alt="A beautiful landscape">
        <figcaption>A beautiful landscape</figcaption>
    </figure>
    <section>
        <h1>Welcome</h1>
        <p>Some welcome text here.</p>
    </section>
</main>

<footer>
    <p>© 2022 Company Name</p>
</footer>
```

</details>

<details>
<summary>
50.<b> How do you create a paragraph or a line break in HTML?</b>
</summary>

In HTML, to create a paragraph, use `<p>...</p>` tags, and to insert a line break, use `<br>` tag.

**Paragraphs in HTML**
Traditional paragraph formatting in HTML is achieved using the <p> tag. The browser's default styling generally adds spacing to the top and bottom of each <p> element, creating distinct paragraphs.

**Syntax**

```jsx harmony
<p>
  This is an example of a paragraph. The text enclosed within the &lt;p&gt; tags
  represents a single paragraph.
</p>
```

**Visual Representation**
This is an example of a paragraph. The text enclosed within the `<p>` tags represents a single paragraph.

**Line Breaks in HTML**
To insert a simple line break in an HTML document, use the `<br>` tag. This tag doesn't require a closing equivalent.

**Syntax**

```jsx harmony
First Line<br>Second Line
```

**Visual Representation**
**First Line**
Second Line (This text doesn't render the line break; it's just to show the raw HTML.)

**Multi-line Text Elements**
In HTML, the `<textarea>` tag allows the input of several lines of text. Nonetheless, it does not auto-format for paragraphs. It wraps text instead, and vertical scroll bars might be enabled, based on the template and content.

Syntax

```jsx harmony
<textarea rows="4" cols="50">
  This is a multi-line text area. It doesn't automatically create separate
  paragraphs. Text wraps based on dimensions supplied.
</textarea>
```

**Visual Representation**

```jsx harmony
<textarea rows="4" cols="50">
  This is a multi-line text area. It doesn't automatically create separate
  paragraphs. Text wraps based on dimensions supplied.
</textarea>
```

</details>

<details>
<summary>
51.<b> What is Character Encoding? </b>
</summary>

Character encoding is a method of converting bytes into characters. To validate or display an HTML document properly, a program must choose a proper character encoding. This is specified in the tag:

```jsx harmony
<meta charset="utf-8" />
```

</details>

<details>
<summary>
52.<b>  What does async and defer refer in script tag? Describe the difference between <script>, <script async> and <script defer></b>
</summary>

- **Async**: Downloads the script file during HTML parsing and will pause the HTML parser to execute it when it has finished downloading.

- **Defer**: Defer downloads the script file during HTML parsing and will only execute it after the HTML parser has completed. Not all browsers support this.

The async attribute is used to indicate to the browser that the script file can be executed asynchronously. The HTML parser does not need to pause at the point it reaches the script tag to fetch and execute, the execution can happen whenever the script becomes ready after being fetched in parallel with the document parsing.

The defer attribute tells the browser to only execute the script file once the HTML document has been fully parsed.

</details>

<details>
<summary>
53.<b> Name 3 ways to decrease page load?</b>
</summary>

- LocalStorage
- Caching resources
- DNS-prefetch (sample below)
- Keep resources on a CDN
</details>

<details>
<summary>
54.<b> What ARIA and screenreaders are, and how to make a website accessible?</b>
</summary>

Screen readers are software programs that provide assistive technologies that allow people with disabilities (such as no sight, sound or mouse-ing ability) to use web applications. You can make your sites more accessible by following ARIA standards such as semantic HTML, alt attributes and using `[role=button]` in the expected ways

</details>

<details>
<summary>
55.<b> What is the purpose of the alt attribute on images?</b>
</summary>

The `alt` attribute provides alternative information for an image if a user cannot view it. The `alt` attribute should be used to describe any images except those which only serve a decorative purposes, in which case it should be left empty.

</details>

<details>
<summary>
56.<b>  Explain some of the pros and cons for CSS animations versus JavaScript animations?</b>
</summary>

Regarding optimization and responsiveness the debate bounces back and forth but, the concept is:

- CSS animations allows the browser to choose where the animation processing is done, CPU or the GPU. (Central or Graphics Processing Unit)

- That said, adding many layers to a document will eventually have a performance hit.

- JS animation means more code for the user to download and for the developer to maintain.

- Applying multiple animation types on an element is harder with CSS since all transforming power is in one property transform

- CSS animations being declarative are not programmable therefore limited in capability.
</details>

<details>
<summary>
57.<b> What does CORS stand for and what issue does it address?</b>
</summary>

`Cross-Origin Resource Sharing (CORS)` is a W3C spec that allows cross-domain communication from the browser. By building on top of the XMLHttpRequest object, CORS allows developers to work with the same idioms as same-domain requests. CORS gives web servers cross-domain access controls, which enable secure cross-domain data transfers.

</details>

<details>
<summary>
58.<b> Ways to improve website performance</b>
</summary>

1. **Minimize HTTP Requests**

**Sites are mainly slow because of too many (or too large) HTTP requests. We can eliminate unnecessary request;**

- **combined files**: js to a file, css to a file
- **CSS sprites**: CSS Sprites are the preferred method for reducing the number of image requests. Combine your background images into a single image and use the CSS background-image and background-position properties to display the desired image segment.

2. **Use a Content Delivery Network CDN**

- A CDN is essentially many optimized servers around the world that deliver web content to users based on their geographic location. This means big performance improvements for site users. Because, say, if a person accessing your site in India, they will be retrieving web content from a server nearby

3. **Optimize Images:**

**image sizes make a huge difference to site speed. The larger content/images, the slower the site. we could:**

- **Changing the resolution**: reducing the “quality” of the image (and thereby the file size)
- **Compressing the picture**: increasing the efficiency of image data storage
- **Cropping the picture**: when cropping, you are cutting out unneeded areas and thus making the image smaller in size

4. **Put Scripts at the Bottom:**

Javascript files can load after the rest of your page. The simplest solution is to place your external Javascript files at the bottom of your page, just before the close of your body tag. Now more of your site can load before your scripts. Another method that allows even more control is to use the defer or async attributes when placing external .js files on your site.

Async tags load the scripts while the rest of the page loads, but this means scripts can be loaded out of order. Basically, lighter files load first. This might be fine for some scripts, but can be disastrous for others.

The defer attribute loads your scripts after your content has finished loading. It also runs the scripts in order. Just make sure your scripts run so late without breaking your site.

Add an Expires or a Cache-Control Header

Web page designs are getting richer and richer, which means more scripts, stylesheets, images, and Flash in the page. A first-time visitor to your page may have to make several HTTP requests, but by using the Expires header you make those components cacheable. This avoids unnecessary HTTP requests on subsequent page views. Expires headers are most often used with images, but they should be used on all components including scripts, stylesheets, and Flash components.
Gzip Components

Compression reduces response times by reducing the size of the HTTP response. Gzipping generally reduces the response size by about 70%.
Put Stylesheets at the Top:

This is because putting stylesheets in the HEAD allows the page to render progressively.
Avoid CSS Expressions

Use GET for AJAX Requests:

Ajax is that it provides instantaneous feedback to the user because it requests information asynchronously from the backend web server
Make JavaScript and CSS External:

Using external files in the real world generally produces faster pages because the JavaScript and CSS files are cached by the browser. JavaScript and CSS that are inlined in HTML documents get downloaded every time the HTML document is requested. This reduces the number of HTTP requests that are needed, but increases the size of the HTML document. On the other hand, if the JavaScript and CSS are in external files cached by the browser, the size of the HTML document is reduced without increasing the number of HTTP requests.
Use get to ajax request:

POST is implemented in the browsers as a two-step process: sending the headers first, then sending data. So it's best to use GET, which only takes one TCP packet to send (unless you have a lot of cookies).
No 404s:

HTTP requests are expensive so making an HTTP request and getting a useless response (i.e. 404 Not Found) is totally unnecessary and will slow down the user experience without any benefit.
Reduce Cookie Size:

HTTP cookies are used for a variety of reasons such as authentication and personalization. Information about cookies is exchanged in the HTTP headers between web servers and browsers. It's important to keep the size of cookies as low as possible to minimize the impact on the user's response time.
Reduce DNS Lookups

Minify JavaScript and CSS

Avoid Redirects

Remove Duplicate Scripts

Configure Etags

Make Ajax Cacheable

Post-load Components

Preload Components

Reduce the Number of DOM Elements

Minimize the Number of iframes

Minimize DOM Access

Optimize CSS Sprites

Don't Scale Images in HTML

Make favicon.ico Small and Cacheable

Avoid Empty Image src

</details>

<details>
<summary>
59.<b> Explain the difference between layout, painting and compositing?</b>
</summary>

**JavaScript**: Typically JavaScript is used to handle work that will result in visual changes, whether it’s jQuery’s animate function, sorting a data set, or adding DOM elements to the page. It doesn’t have to be JavaScript that triggers a visual change, though: CSS Animations, Transitions, and the Web Animations API are also commonly used.

**Style calculations**: This is the process of figuring out which CSS rules apply to which elements based on matching selectors, for example, .headline or .nav > .nav\_\_item. From there, once rules are known, they are applied and the final styles for each element are calculated.

**Layout**: Once the browser knows which rules apply to an element it can begin to calculate how much space it takes up and where it is on screen. The web’s layout model means that one element can affect others, for example the width of the element typically affects its children’s widths and so on all the way up and down the tree, so the process can be quite involved for the browser.

**Paint**: Painting is the process of filling in pixels. It involves drawing out text, colors, images, borders, and shadows, essentially every visual part of the elements. The drawing is typically done onto multiple surfaces, often called layers.

**Compositing**: Since the parts of the page were drawn into potentially multiple layers they need to be drawn to the screen in the correct order so that the page renders correctly. This is especially important for elements that overlap another, since a mistake could result in one element appearing over the top of another incorrectly.

</details>

<details>
<summary>
60.<b>  Why you would like to use semantic tag?</b>
</summary>

1. Search Engine Optimization, accessibility, repurposing, light code.
2. Many visually impaired person rely on browser speech and semantic tag helps to interpret page content clearly.
3. Search engine needs to understand page content to rank and semantic tag helps.
4. Semantic code aids accessibility. Specially, many people whose eyes are not good rely on speech browsers to read pages to them. These programs cannot interpret pages very well unless they are clearly explained.
5. Help Search engines to better understand pages. Search engine need to understand what your content is about when rank you properly on search engines. Semantic code tends to improve your placement on search engines, as it is easier for the "search engine spiders" to understand.
6. It’s easier to read and edit, which saves time and money during maintenance.
</details>

<details>
<summary>
61.<b> How to make page responsive?</b>
</summary>

Responsive Web Design is about using HTML and CSS to automatically resize, hide, shrink, or enlarge, a website, to make it look good on all devices (desktops, tablets, and phones).

1. Setting the viewport

```jsx harmony
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

2. Responsive Images
   If the CSS width property is set to 100%, the image will be responsive and scale up and down

```jsx harmony
<img src="img.png" style="width:100%;">
```

3. Show different Images depending on Browser Width
   The HTML <picture> element allows you to define different images for different browser window sizes.

```jsx harmony
<picture>
  <source srcset="img_small.jpg" media="(max-width: 600px)">
  <source srcset="img_large.jpg" media="(max-width: 1500px)">
  <source srcset="img.jpg">
  <img src="img_small.jpg" alt="Image">
</picture>
```

4. Responsive Text Size
   The text size can be set with a "vw" unit, which means the "viewport width". That way the text size will follow the size of the browser window.

```jsx harmony
<h1 style="font-size:10vw">Hello World</h1>
```

5. Media Queries
   Using media queries you can define completely different styles for different browser sizes.

```jsx harmony
/* Use a media query to add a breakpoint at 800px: */
@media screen and (max-width: 800px) {
  .left, .main, .right {
    width: 100%; /* The width is 100%, when the viewport is 800px or smaller */
  }
}
```

</details>

<details>
<summary>
62.<b>What is difference between span tag and div tag?</b>
</summary>

The primary difference between a div and a span is their default behavior. By default,
a <div> is a `block-level-element` and a <span> is an `inline element`.

```jsx harmony
<div>
  Demo Text, with <span>some other</span> text.
</div>
```

</details>

<details>
<summary>
63.<b> What are optional closing tag?</b>
</summary>

`<p>, <li>, <td>, <tr>, <th>, <html>, <body>`, etc. don't have to provide end tag. Whenever browser hits a new tag it automatically ends the previous tag.

</details>

<details>
<summary>
64.<b> What is the purpose of meta tags? </b>
</summary>

The META elements can be used to include name/value pairs describing properties of the `HTML` document, such as author, expiry date, a list of keywords, document author etc.

```jsx harmony
<!DOCTYPE html>
<html>
  <head>
        <!--Recommended Meta Tags-->
        <meta charset="utf-8">
        <meta name="language" content="english">
        <meta http-equiv="content-type" content="text/html">
        <meta name="author" content="Author Name">
        <meta name="designer" content="Designer Name">
        <meta name="publisher" content="Publisher Name">
        <meta name="no-email-collection" content="name@email.com">
        <meta http-equiv="X-UA-Compatible" content="IE=edge"/>

        <!--Search Engine Optimization Meta Tags-->
        <meta name="description" content="Project Description">
        <meta name="keywords" content="Software Engineer,Product Manager,Project Manager,Data Scientist">
        <meta name="robots" content="index,follow">
        <meta name="revisit-after" content="7 days">
        <meta name="distribution" content="web">
        <meta name="robots" content="noodp">

        <!--Optional Meta Tags-->
        <meta name="distribution" content="web">
        <meta name="web_author" content="">
        <meta name="rating" content="">
        <meta name="subject" content="Personal">
        <meta name="title" content=" - Official Website.">
        <meta name="copyright" content="Copyright 2020">
        <meta name="reply-to" content="">
        <meta name="abstract" content="">
        <meta name="city" content="Bangalore">
        <meta name="country" content="INDIA">
        <meta name="distribution" content="">
        <meta name="classification" content="">

        <!--Meta Tags for HTML pages on Mobile-->
        <meta name="format-detection" content="telephone=yes"/>
        <meta name="HandheldFriendly" content="true"/>
        <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
        <meta name="apple-mobile-web-app-capable" content="yes" />

        <!--http-equiv Tags-->
        <meta http-equiv="Content-Style-Type" content="text/css">
        <meta http-equiv="Content-Script-Type" content="text/javascript">

    <title>HTML5 Meta Tags</title>
  </head>
  <body>
       ...
  </body>
</html>

```

</details>

<details>
<summary>
65.<b> Can you describe the difference between progressive enhancement and graceful degradation?</b>
</summary>

- **Graceful degradation** is when you initially serve the best possible user experience, with all modern functionality,
  but use feature detection to “gracefully degrade” parts of your application with a fallback or polyfill.

- **Progressive enhancement** ensures a page works at the lowest expected abilities of browsers.
  So if you have a JavaScript web application that enhances a persons ability to send information to a database with features like ajax – at the very least you need to provide the ability for a person to send that same information without JavaScript enabled. In this case a simple form with full-page refresh will do what you need.

</details>

<details>
<summary>
66.<b> What is the purpose of cache busting and how can you achieve it?</b>
</summary>

Browsers have a cache to temporarily store files on websites so they don't need to be re-downloaded again when switching between pages or reloading the same page. The server is set up to send headers that tell the browser to store the file for a given amount of time. This greatly increases website speed and preserves bandwidth.

However, it can cause problems when the website has been changed by developers because the user's cache still references old files. This can either leave them with old functionality or break a website if the cached CSS and JavaScript files are referencing elements that no longer exist, have moved or have been renamed.

**Cache busting** is the process of forcing the browser to download the new files. This is done by naming the file something different to the old file.

A common technique to force the browser to re-download the file is to append a query string to the end of the file.

```jsx harmony
<!-- src="js/script.js" => src="js/script.js?v=2" -->
<script src="js/script.js?v=2"></script>
```

The browser considers it a different file but prevents the need to change the file name.

</details>

<details>
<summary>
67.<b> Explain some of the pros and cons for CSS animations versus JavaScript animations?</b>
</summary>

Regarding optimization and responsiveness the debate bounces back and forth but, the concept is:

1. CSS animations allows the browser to choose where the animation processing is done, CPU or the GPU. (Central or Graphics Processing Unit)
2. That said, adding many layers to a document will eventually have a performance hit.
3. JS animation means more code for the user to download and for the developer to maintain.
4. Applying multiple animation types on an element is harder with CSS since all transforming power is in one property transform
5. CSS animations being declarative are not programmable therefore limited in capability.
</details>

<details>
<summary>
68.<b> What does the lang attribute in html do?</b>
</summary>

Helps in styling pages by using them in css :`lang()` pseudo class Spelling and grammar checkers Languade detection by search engines

</details>

<details>
<summary>
69.<b> What is desktop first and mobile first design approach?</b>
</summary>

**Desktop first** : General selectors and styles designed to make the site look good on DESKTOP screens defined globally. But they affect all devices, and must be overridden by max-width media queries targeting minimum screen size

**Mobile First** : General selectors and styles designed to make the site look good on small MOBILE screens go here. But they affect all devices, and must be overridden by min-width media queries targeting maximum scrren size

In desktop first approach the media queries will be written with respect to max-width whereas in mobile first approach media queries will be written with respect to min-width

</details>

<details>
<summary>
70.<b> Explain Microdata in HTML5?</b>
</summary>

**Microdata** is a standardized way to provide additional semantics in web pages. Microdata lets you define your own customized elements and start embedding custom properties in your web pages. At a high level, microdata consists of a group of name-value pairs.

The groups are called items, and each name-value pair is a **property**. Items and properties are represented by regular elements. Search engines benefit greatly from direct access to this structured data because it allows search engines to understand the information on web pages and provide more relevant results to users.

At a high level, microdata consists of a group of name-value pairs

`itemscope`:- To create an item
`itemprop`:- To add a property to an item
Example

```jsx harmony
<div itemscope>
    <p>My name is <span itemprop="name">Elizabeth</span>.</p>
</div>

<div itemscope>
    <p>My name is <span itemprop="name">Daniel</span>.</p>
</div>
```

</details>
