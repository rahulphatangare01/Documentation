# Express Interview Questions

## Express Basic Interview Questions

<details>
<summary>
1.  <b> What is Express.js? </b>
</summary>

**Express.js** is a web application framework that runs on Node.js. It simplifies the process of building web applications and APIs by providing a range of powerful features, including robust routing, middleware support, and HTTP utility methods. Thanks to its modular design, you can expand its functionality through additional libraries and Node.js modules.

**Key Features**

- **Middleware**: Express.js makes use of middleware functions that have access to the request-response cycle. This allows for a variety of operations such as logging, authentication, and data parsing.

- **Routing**: The framework offers a flexible and intuitive routing system, making it easy to handle different HTTP request methods on various URLs.

- **Templates**: Integrated support for template engines enables the dynamic rendering of HTML content.

- **HTTP Methods**: It provides built-in methods for all HTTP requests, such as get, post, put, delete, simplifying request handling.

- **Error Handling**: Express streamlines error management, and its middleware functions can specifically handle errors.

- **RESTful APIs**: Its features such as request and response object chaining, along with HTTP method support, make it ideal for creating RESTful APIs.

</details>

<details>
<summary>
2.  <b>Express.js how does it relate to Node.js </b>
</summary>

**Relationship with Node.js**

- `Express.js` is a web application framework specifically designed to extend the capabilities of Node.js for web development. Node.js, on the other hand, is a cross-platform JavaScript runtime environment that allows developers to build server-side and networking applications.
- Express.js accomplishes this through a layer of abstractions and a more structured approach, which Node.js, by itself, doesn't provide out of the box.

**Code Example: Basic Express Server**

```jsx harmony
// Import required modules
const express = require("express");

// Create an Express application
const app = express();
const port = 3000;

// Define a route and its callback function
app.get("/", (req, res) => {
  res.send("Hello World!");
});

// Start the server
app.listen(port, () => {
  console.log(`Server running at http://localhost:${port}/`);
});
```

</details>

<details>
<summary>
3.  <b>Explain the concept of middleware in Express.js. </b>
</summary>

`Middleware` acts as a bridge between incoming HTTP requests and your Express.js application, allowing for a range of operations such as parsing request bodies, handling authentication, and even serving static files.

**Middleware Functions**

- A middleware function in Express is a handler invoked in sequence when an HTTP request is received. It has access to the request and response objects, as well as the next function to trigger the next middleware in line.
- Each middleware function typically follows this signature:

```jsx harmony
function middlewareFunction(req, res, next) {
  // ...middleware logic
  next(); // or next(err); based on whether to proceed or handle an error
}
```

Note that the `next()` call is essential to move on to the next middleware.

**Types of Middleware**

- **Application-Level Middleware**
  Registered via app.use(middlewareFunction), it's active for every incoming request, making it suitable for tasks like request logging or establishing cross-cutting concerns.

- **Router-Level Middleware**
  Operates on specific router paths and is defined using router.use(middlewareFunction). It's useful for tasks related to particular sets of routes.

- **Error-Handling Middleware**
  Recognizable via its function signature (err, req, res, next), this type of middleware specifically handles errors. In the middleware chain, it should be placed after regular middlewares and can be added using app.use(function(err, req, res, next) { ... }).

- **Built-In Middleware**
  Express offers ready-to-use middleware for tasks like serving static files or parsing the request body.

**Middleware Chaining**

- By sequentially calling `next()` within each middleware, you form a chain, facilitating a cascade of operations for an incoming request.

- Consider a multi-tiered security setup, for example, with authentication, authorization, and request validation. Only when a request passes through all three tiers will it be processed by the actual route handler.

**Code Example: Middleware Chaining**

```jsx harmony
const express = require("express");
const app = express();

// Sample middleware functions
function authenticationMiddleware(req, res, next) {
  console.log("Authenticating...");
  next();
}

function authorizationMiddleware(req, res, next) {
  console.log("Authorizing...");
  next();
}

function requestValidationMiddleware(req, res, next) {
  console.log("Validating request...");
  next();
}

// The actual route handler
app.get(
  "/my-secured-endpoint",
  authenticationMiddleware,
  authorizationMiddleware,
  requestValidationMiddleware,
  (req, res) => {
    res.send("Welcome! You are authorized.");
  }
);

app.listen(3000);
```

</details>

<details>
<summary>
4.  <b> How would you set up a basic Express.js application? </b>
</summary>

To set up a basic Express.js application, follow these steps:

1. Initialize the Project
   Create a new directory for your project and run npm init to generate a package.json file.

2. Install Dependencies
   Install Express as a dependency using the Node Package Manager (NPM):

```jsx harmony
npm install express
```

3. Create the Application
   In your project directory, create a main file (usually named app.js or index.js) to set up the Express application.

Here is the JavaScript code:

```jsx harmony
// Import the Express module
const express = require("express");

// Create an Express application
const app = express();

// Define a sample route
app.get("/", (req, res) => {
  res.send("Hello, World!");
});

// Start the server
const port = 3000;
app.listen(port, () => {
  console.log(`Server running on port ${port}`);
});
```

4. Run the Application
   You can start your Express server using Node.js:

```jsx harmony

node app.js
```

For convenience, you might consider using Nodemon as a development dependency which automatically restarts the server upon file changes.

</details>

<details>
<summary>
5.  <b> How to get the name parameters in express?</b>
</summary>

This property is an object containing properties mapped to the named route “parameters”. For example, if you have the route /user/:name, then the “name” property is available as req.params.name. This object defaults to {}.

```jsx harmony
// GET /user/tj
req.params.name;
// => "tj"
```

</details>

<details>
<summary>
6.  <b> What is the purpose of the app.use() function?</b>
</summary>

- In Express.js, the` app.use()` function is a powerful tool for middleware management. It can handle HTTP requests and responses, as well as prepare data or execute processes in between.

**Key Functions**

1. **Global Middleware**: Without a specified path, the middleware will process every request.
2. **Route-specific Middleware**: When given a path, the middleware will only apply to the matched routes.
   Common Use-Cases
3. **Body Parsing**: To extract data from incoming requests, especially useful for POST and PUT requests.

```jsx harmony
const bodyParser = require("body-parser");
app.use(bodyParser.json());
```

4. **Handling CORS**: Useful in API applications to manage cross-origin requests.

```jsx harmony
app.use(function (req, res, next) {
  res.header("Access-Control-Allow-Origin", "*");
  res.header(
    "Access-Control-Allow-Headers",
    "Origin, X-Requested-With, Content-Type, Accept"
  );
  next();
});
```

5. **Static File Serving**: For serving files like images, CSS, or client-side JavaScript.

```jsx harmony
app.use(express.static("public"));
```

6. **Logging**: To record request details for debugging or analytics.

```jsx harmony
app.use(function (req, res, next) {
  console.log(`${new Date().toUTCString()}: ${req.method} ${req.originalUrl}`);
  next();
});
```

7. **Error Handling**: To manage and report errors during request processing.

```jsx harmony
app.use(function (err, req, res, next) {
  console.error(err);
  res.status(500).send("Internal Server Error");
});
```

**Chaining Middleware**
You can stack multiple middleware using app.use() in the order they need to execute. For a matched route, control can be passed to the next matching route or terminated early using next().

</details>

<details>
<summary>
7.  <b>How do you serve static files using Express.js? </b>
</summary>

In an Express.js web application, you often need to serve static files such as stylesheets, client-side JavaScript, and images. You can accomplish this using the `express.static` middleware.

**Middleware for Serving Static Files**
The `express.static` middleware function serves static files and is typically used to serve assets like images, CSS, and client-side JavaScript.

**code example**:

```jsx hramony
app.use(express.static("public"));
```

In this example, the folder named `public` will be used to serve the static assets.

**Additional Configuration with Method Chaining**
You can further configure the behavior of the `express.static` middleware by chaining methods.

For example, to set the cache-control header, the code looks like this:

```jsx harmony
app.use(
  express.static("public", {
    maxAge: "1d",
  })
);
```

Here, the `'1d'` ensures that caching is enabled for a day.

**Using a Subdirectory**
If you want to serve files from a subdirectory, you can specify it when using the express.static middleware.

**code example**:

```jsx haromy
app.use("/static", express.static("public"));
```

This serves the files from the public folder but any requests for these files should start with /static.

**What express.static Serves**

1. Images: PNG, JPEG, GIF
2. Text Content: HTML, CSS, JavaScript
3. Fonts
4. JSON Data
5. Not for dynamic content
6. While express.static is excellent for static assets, it's not suitable for dynamic content or data in POST requests.

Not for dynamic content
While `express.static` is excellent for static assets, it's not suitable for dynamic content or data in `POST` requests.

</details>

<details>
<summary>
8.  <b>Discuss the difference between app.get() and app.post() in Express.js. </b>
</summary>

In Express.js, `app.get()` and `app.post()` are two of the most commonly used HTTP method middleware. The choice between them (or using both) typically depends on whether you are retrieving or submitting/persisting data.

**Key Distinctions**
HTTP Verbs: External Visibility

- **app.get()**: Listens for GET requests. Designed for data retrieval. Visible URLs typically trigger such requests (e.g., links or direct URL entry in the browser).

- **app.post()**: Listens for POST requests. Intended for data submission. Typically not visible in the URL bar, commonly used for form submissions.

Data Transmission

- **app.get():** Uses query parameters for data transmission, visible in the URL. Useful for simple, non-sensitive, read-only data (e.g., filtering or pagination).

- **app.post():** Uses request body for data transmission, which can be in various formats (e.g., JSON, form data). Ideal for more complex data, file uploads, or sensitive information.

**Using Both `app.get() `and `app.post()` for the Same Route**
There are cases, especially for RESTful design, where a single URL needs to handle both data retrieval and data submission.

**Resource Retrieval and Creation:**

- Fetch a Form: Use app.get() to return a form for users to fill out.
- Form Submission: Use app.post() to process and save the submitted form data.
  **Complete Entity Modification**: For a complete update (or replacement in REST), using `app.post()` ensures that the update action is triggered via a post request, not a get request. This distiction is important to obey the RESTful principles.

**Code Example:** **Using both app.get() and app.post() for a single route**
Here is the JavaScript code:

```jsx harmony
const userRecords = {}; // in-memory "database" for the sake of example

// Handle user registration form
app.get("/users/register", (req, res) => {
  res.send(
    'Please register: <form method="POST"><input name="username"></form>'
  );
});

// Process submitted registration form
app.post("/users/register", (req, res) => {
  userRecords[req.body.username] = req.body;
  res.send("Registration complete");
});
```

</details>

<details>
<summary>
9.  <b> How do you retrieve the URL parameters from a GET request in Express.js?</b>
</summary>

In Express.js, you can extract URL parameters from a GET request using the `req.params` object. Here's a quick look at the steps and the code example:

**Code Example: Retrieving URL Parameters**

```jsx harmony
// Sample URL: http://example.com/users/123
// Relevant Route: /users/:id

// Define the endpoint/route
app.get("/users/:id", (req, res) => {
  // Retrieve the URL parameter
  const userId = req.params.id;
  // ... (rest of the code)
});
```

In this example, the URL parameter `id` is extracted and used to fetch the corresponding user data.

**Additional Steps for Complex GET Requests**
For simple and straightforward **GET** requests, supplying URL parameters directly works well. However, for more complex scenarios, such as parsing parameters from a URL with the help of `querystrings` or handling optional parameters, Express.js offers more advanced techniques which are outlined below:

**Parsing Query Parameters**
**What It Is**: Additional data passed in a URL after the ? character. Example: `http://example.com/resource?type=user&page=1.`

**How to Access It**: Use req.query, an object that provides key-value pairs of the parsed query parameters.

**Code Example: Parsing Query Parameters**

```jsx harmony
app.get("/search", (req, res) => {
  const { q, category } = req.query;
  // ... (rest of the code)
});
```

**Optional and Catch-All Segments**

- **Optional Segments**: URL segments enclosed in parentheses are optional and can be accessed using req.params. Example: `/book(/:title)`

- **Catch-All Segments**: Captures the remainder of the URL and is useful in cases like URL rewriting. Denoted by an asterisk (_) or double asterisk `(\*\*)`. Accessed using `req.params` as well. Example: `/documents/_`

</details>

<details>
<summary>
10.  <b>  What are route handlers, and how would you implement them? </b>
</summary>

**Route handlers** in Express.js are middleware functions designed to manage specific paths in your application.

Depending on the HTTP method and endpoint, they can perform diverse tasks, such as data retrieval from a database, view rendering, or HTTP response management.

**Code Example: Setting Up a Simple Route Handler**
Here is the code:

```jsx harmony
// Responds with "Hello, World!" for GET requests to the root URL (/)
app.get("/", (req, res) => {
  res.send("Hello, World!");
});
```

In this example, the route handler is `(req, res) => { res.send('Hello, World!'); }`. It listens for GET requests on
the root URL and responds with "Hello, World!".

**What Are Route-Handler Chains?**
You can associate numerous route-managing middleware functions to a single route. Every middleware function in the chain has to either proceed to the following function using `next()` or conclude the request-response cycle.

This allows for checks like user authentication before accessing a route.

**HTTP Method Convenience Methods**
Express.js offers specialized, highly-readable methods for the most common HTTP requests:

1. `app.get()`
2. `app.post()`
3. `app.put()`
4. `app.delete()`
5. `app.use()`
These methods streamline route handling setup.
</details>

<details>
<summary>
11.  <b> </b>
</summary>
</details>

<details>
<summary>
12.  <b> </b>
</summary>
</details>

<details>
<summary>
13.  <b> </b>
</summary>
</details>

<details>
<summary>
14.  <b> </b>
</summary>
</details>

<details>
<summary>
15.  <b> </b>
</summary>
</details>

<details>
<summary>
16.  <b> </b>
</summary>
</details>

<details>
<summary>
17.  <b> </b>
</summary>
</details>

<details>
<summary>
18.  <b> </b>
</summary>
</details>

<details>
<summary>
19.  <b> </b>
</summary>
</details>

<details>
<summary>
20.  <b> </b>
</summary>
</details>

<details>
<summary>
21.  <b> </b>
</summary>
</details>

<details>
<summary>
22.  <b> </b>
</summary>
</details>

<details>
<summary>
23.  <b> </b>
</summary>
</details>

<details>
<summary>
24.  <b> </b>
</summary>
</details>

<details>
<summary>
25.  <b> </b>
</summary>
</details>

<details>
<summary>
26.  <b> </b>
</summary>
</details>

<details>
<summary>
27.  <b> </b>
</summary>
</details>

<details>
<summary>
28.  <b> </b>
</summary>
</details>

<details>
<summary>
29.  <b> </b>
</summary>
</details>

<details>
<summary>
30.  <b> </b>
</summary>
</details>

<details>
<summary>
31.  <b> </b>
</summary>
</details>

<details>
<summary>
32.  <b> </b>
</summary>
</details>

<details>
<summary>
33.  <b> </b>
</summary>
</details>

<details>
<summary>
34.  <b> </b>
</summary>
</details>

<details>
<summary>
35.  <b> </b>
</summary>
</details>
