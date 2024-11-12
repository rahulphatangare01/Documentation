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
<summary>
37.<b></b>
</summary>
</details>

<details>
<summary>
38.<b></b>
</summary>
</details>

<details>
<summary>
39.<b></b>
</summary>
</details>

<details>
<summary>
40.<b></b>
</summary>
</details>

<details>
<summary>
41.<b></b>
</summary>
</details>

<details>
<summary>
42.<b></b>
</summary>
</details>

<details>
<summary>
43.<b></b>
</summary>
</details>

<details>
<summary>
44.<b></b>
</summary>
</details>

<details>
<summary>
45.<b></b>
</summary>
</details>

<details>
<summary>
46.<b></b>
</summary>
</details>

<details>
<summary>
47.<b></b>
</summary>
</details>

<details>
<summary>
48.<b></b>
</summary>
</details>

<details>
<summary>
49.<b></b>
</summary>
</details>

<details>
<summary>
50.<b></b>
</summary>
</details>

<details>
<summary>
51.<b></b>
</summary>
</details>

<details>
<summary>
52.<b></b>
</summary>
</details>

<details>
<summary>
53.<b></b>
</summary>
</details>

<details>
<summary>
54.<b></b>
</summary>
</details>

<details>
<summary>
55.<b></b>
</summary>
</details>

<details>
<summary>
56.<b></b>
</summary>
</details>

<details>
<summary>
57.<b></b>
</summary>
</details>

<details>
<summary>
58.<b></b>
</summary>
</details>

<details>
<summary>
59.<b></b>
</summary>
</details>

<details>
<summary>
60.<b></b>
</summary>
</details>

<details>
<summary>
61.<b></b>
</summary>
</details>

<details>
<summary>
62.<b></b>
</summary>
</details>

<details>
<summary>
63.<b></b>
</summary>
</details>

<details>
<summary>
64.<b></b>
</summary>
</details>

<details>
<summary>
65.<b></b>
</summary>
</details>

<details>
<summary>
66.<b></b>
</summary>
</details>

<details>
<summary>
67.<b></b>
</summary>
</details>

<details>
<summary>
68.<b></b>
</summary>
</details>

<details>
<summary>
69.<b></b>
</summary>
</details>

<details>
<summary>
70.<b></b>
</summary>
</details>

<details>
<summary>
71.<b></b>
</summary>
</details>

<details>
<summary>
72.<b></b>
</summary>
</details>

<details>
<summary>
73.<b></b>
</summary>
</details>

<details>
<summary>
74.<b></b>
</summary>
</details>

<details>
<summary>
75.<b></b>
</summary>
</details>

<details>
<summary>
76.<b></b>
</summary>
</details>

<details>
<summary>
77.<b></b>
</summary>
</details>

<details>
<summary>
78.<b></b>
</summary>
</details>

<details>
<summary>
79.<b></b>
</summary>
</details>

<details>
<summary>
80.<b></b>
</summary>
</details>

<details>
<summary>
81.<b></b>
</summary>
</details>

<details>
<summary>
82.<b></b>
</summary>
</details>

<details>
<summary>
83.<b></b>
</summary>
</details>

<details>
<summary>
84.<b></b>
</summary>
</details>

<details>
<summary>
85.<b></b>
</summary>
</details>

<details>
<summary>
86.<b></b>
</summary>
</details>

<details>
<summary>
87.<b></b>
</summary>
</details>

<details>
<summary>
88.<b></b>
</summary>
</details>

<details>
<summary>
89.<b></b>
</summary>
</details>

<details>
<summary>
90.<b></b>
</summary>
</details>

<details>
<summary>
91.<b></b>
</summary>
</details>

<details>
<summary>
92.<b></b>
</summary>
</details>

<details>
<summary>
93.<b></b>
</summary>
</details>

<details>
<summary>
94.<b></b>
</summary>
</details>

<details>
<summary>
95.<b></b>
</summary>
</details>

<details>
<summary>
96.<b></b>
</summary>
</details>

<details>
<summary>
97.<b></b>
</summary>
</details>

<details>
<summary>
98.<b></b>
</summary>
</details>

<details>
<summary>
99.<b></b>
</summary>
</details>

<details>
<summary>
100.<b></b>
</summary>
</details>
