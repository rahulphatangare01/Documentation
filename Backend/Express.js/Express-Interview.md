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
6.  <b> </b>
</summary>
</details>

<details>
<summary>
7.  <b> </b>
</summary>
</details>

<details>
<summary>
8.  <b> </b>
</summary>
</details>

<details>
<summary>
9.  <b></b>
</summary>
</details>

<details>
<summary>
10.  <b> </b>
</summary>
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
