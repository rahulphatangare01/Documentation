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
11.  <b> How do you enable CORS in an Express.js application?</b>
</summary>

**Cross-Origin Resource Sharing (CORS)** is a mechanism that allows web pages to make requests to a different domain. In Express.js, you can enable CORS using the cors package or by setting headers manually.

**Using the cors Package**

1. Install `cors`:

Use npm or yarn to install the `cors` package.

```jsx harmony
npm install cors
```

2. Integrate with Your Express App:

Use the app.use(cors()) middleware. You can also customize CORS behavior with options.

```jsx harmony
const express = require("express");
const cors = require("cors");
const app = express();

// Enable CORS for all routes
app.use(cors());

// Example: Enable CORS only for a specific route
app.get("/public-data", cors(), (req, res) => {
  // ...
});

// Example: Customize CORS options
const customCorsOptions = {
  origin: "https://example.com",
  optionsSuccessStatus: 200, // Some legacy browsers choke on 204
};

app.use(cors(customCorsOptions));
```

**Manual CORS Setup**
Use the following code example to set **CORS** headers manually in your Express app:

```jsx harmony
app.use((req, res, next) => {
  res.header("Access-Control-Allow-Origin", "*");
  res.header(
    "Access-Control-Allow-Headers",
    "Origin, X-Requested-With, Content-Type, Accept"
  );
  if (req.method === "OPTIONS") {
    res.header(
      "Access-Control-Allow-Methods",
      "GET, POST, PUT, PATCH, DELETE, OPTIONS"
    );
    return res.status(200).json({});
  }
  next();
});
```

Make sure to place this middleware before your route definitions.

</details>

<details>
<summary>
12.  <b>  Explain the use of next() in Express.js middleware.</b>
</summary>

In Express.js, **middleware** functions are crucial for handling HTTP requests. A single request can pass through multiple middlewares before reaching its endpoint, providing opportunities for tasks like logging, data parsing, and error handling. The **next()** function is instrumental in this process, allowing for both regular middleware chaining and special error handling.

**What is next()?**

- **next():** A callback function that, when called within a middleware, passes control to the next middleware in the stack.
- `next()` is typically invoked to signal that a middleware has completed its tasks and that the request should move on to the next middleware.
  If a middleware doesn't call `next()`, the request flow can get stuck, and the subsequent middlewares won't be executed.

**Use-Cases**

1. **Regular Flow**: Invoke `next()` to move the request and response objects through the middleware stack.
2. **Error Handling**: If a middleware detects an error, it can short-circuit the regular flow and jump directly to an error-handling middleware (defined with `app.use(function(err, req, res, next) {}))`. This is achieved by calling `next(err)`, where`err`is the detected error.

**Code Example: Logging Middleware**
Here is the code:

```jsx harmony
const app = require("express")();

// Sample middleware: logs the request method and URL
app.use((req, res, next) => {
  console.log(`${req.method} ${req.url}`);
  next(); // Move to the next middleware
});

// Sample middleware: logs the current UTC time
app.use((req, res, next) => {
  console.log(new Date().toUTCString());
  next(); // Move to the next middleware
});

app.listen(3000);
```

In this example, both middlewares call `next()` to allow the request to progress to the next logging middleware and eventually to the endpoint (not shown, but would be the next in the chain).

Without the `next()` calls, the request would get stuck after the first middleware.

</details>

<details>
<summary>
13.  <b> What is the role of the express.Router class? </b>
</summary>

The `express.Router` is a powerful tool for managing multiple route controllers. It helps in organizing routes and their handling functions into modular, self-contained groups.

**Key Features**

1. **Modularity**: Rely on separate route modules for improved code organization, maintainability, and collaboration.

2. **Middlewares**: Like the main express app, the router can also use middlewares to process incoming requests.

3. **HTTP Method Chaining**: Simplifies route handling by allowing method-specific routes to be defined using method names.

**Example: Middleware and Route Handling**

```jsx harmony
const express = require("express");
const router = express.Router();

// Logger Middleware
router.use((req, res, next) => {
  console.log("Router-specific Request Time:", Date.now());
  next();
});

// "GET" method route
router.get("/", (req, res) => {
  res.send("Router Home Page");
});

// "POST" method route
router.post("/", (req, res) => {
  res.send("Router Home Page - POST Request");
});

module.exports = router;
```

In this example, we:

- Utilize the built-in express.Router.
- Attach a general-purpose middleware and two different HTTP method-specific routes.
- The router is then integrated into the main express app using:

```jsx harmony
const app = express();
const router = require("./myRouterModule");

app.use("/routerExample", router);
```

Here, `app.use('/routerExample', router);` assigns all routes defined in the router to /routerExample.

</details>

<details>
<summary>
14.  <b> How do you handle 404 errors in Express.js?</b>
</summary>

`Handling 404 errors` in Express is essential for capturing and responding to requests for non-existent resources. You typically use both middleware and `HTTP response` mechanisms for this purpose.

**Middleware for 404s**
Use `app.use `at the end of the middleware chain to capture unresolved routes.
Invoke the middleware with next() and an Error object to forward to the error-handling middleware.
Here is the Node.js code example:

```jsx harmony
app.use((req, res, next) => {
  const err = new Error(`Not Found: ${req.originalUrl}`);
  err.status = 404;
  next(err);
});
```

**Error-Handling Middleware for 404s and Other Errors**

1. Define an error-handling middleware with four arguments. The first one being the error object.
2. Check the error's status and respond accordingly. If it's a 404, handle it as a not-found error; otherwise, handle it as a server error.
   Here is the Node.js code:

```jsx harmony
app.use((err, req, res, next) => {
  const status = err.status || 500;
  const message = err.message || "Internal Server Error";

  res.status(status).send(message);
});
```

**Full Example:**
Here is the complete Node.js application:

```jsx harmony
const express = require("express");
const app = express();
const port = 3000;

// Sample router for demonstration
const usersRouter = express.Router();
usersRouter.get("/profile", (req, res) => {
  res.send("User Profile");
});
app.use("/users", usersRouter);

// Capture 404s
app.use((req, res, next) => {
  const err = new Error(`Not Found: ${req.originalUrl}`);
  err.status = 404;
  next(err);
});

// Error-handling middleware
app.use((err, req, res, next) => {
  const status = err.status || 500;
  const message = err.message || "Internal Server Error";
  res.status(status).send(message);
});

app.listen(port, () => {
  console.log(`Example app listening at http://localhost:${port}`);
});
```

</details>

<details>
<summary>
15.  <b> What are the differences between req.query and req.params?</b>
</summary>

In Express.js, `req.query` is used to access GET request parameters, while `req.params` is used to capture parameters defined in the **URL path**.

**Understanding Express.js Routing**
Express.js uses app.get() and similar functions to handle different types of HTTP requests.

- **app.get**('/users/:id'): Matches GET requests to `/users/123` where `123` is the `:id` parameter in the path.

**Accessing Request Data**
**req.query**: Utilized to extract query string parameters from the request URL. Example: For the URL` /route?id=123`, use `req.query`.id to obtain 123.
**req.params**: Used to retrieve parameters from the request URL path. For the route `/users/:id`, use `req.params.id` to capture the ID, such as for `/users/123`.

**Code Example: Request Data**
Here is the Express.js server setup:

```jsx harmony
const express = require("express");
const app = express();
const port = 3000;

// Endpoint to capture query string parameter
app.get("/query", (req, res) => {
  console.log(req.query);
  res.send("Received your query param!");
});

// Endpoint to capture URL parameter
app.get("/user/:id", (req, res) => {
  console.log(req.params);
  res.send("Received your URL param!");
});

app.listen(port, () => console.log(`Listening on port ${port}!`));
```

</details>

<details>
<summary>
16.  <b>  Describe the purpose of req.body and how you would access it. </b>
</summary>

In an Express.js application, `req.body` is a property of the HTTP request object that contains data submitted through an `HTTP POST` request.

The POST request might originate from an HTML form, a client-side JavaScript code, or another API client. The data in `req.body` is typically structured as a JSON object or a URL-encoded form.

**Middleware and Parsing Request Body**

The `express.json()` and `express.urlencoded()` middleware parse incoming Request objects before passing them on. These middlewares populate `req.body` with the parsed JSON and URL-encoded data, respectively.

Here is an example of how you might set up body parsing in an Express app:

```jsx harmony
const express = require("express");
const app = express();

// Parse JSON and URL-encoded data into req.body
app.use(express.json());
app.use(express.urlencoded({ extended: true }));
```

**Accessing req.body Data**

- Once the body parsing middleware is in place, you can access the parsed data in your route handling functions:

- **POST or PUT Requests**: When a client submits a POST or PUT request with a JSON payload in the request body, you can access this data through req.body.
  Here is an example:

**Client-side JavaScript:**

```jsx harmony
fetch("/example-route", {
  method: "POST",
  headers: {
    "Content-Type": "application/json",
  },
  body: JSON.stringify({ key: "value" }),
});
```

**Server-side Express route handler:**

```jsx harmony
app.post("/example-route", (req, res) => {
  console.log(req.body); // Outputs: { key: 'value' }
});
```

**HTML Forms**: When a form is submitted using <form> with action pointing to your Express route and method as POST or PUT, and the form fields are input elements within the form, req.body will contain these form field values.
Here is an example:

**HTML form**:

```jsx harmony
<form action="/form-endpoint" method="POST">
  <input type="text" name="username" />
  <input type="password" name="password" />
  <button type="submit">Submit</button>
</form>
```

**Express route:**

```jsx harmony
app.post("/form-endpoint", (req, res) => {
  console.log(req.body.username, req.body.password);
});
```

A modern technique for sending form data using fetch is by setting the Content-Type header to 'application/x-www-form-urlencoded' and using the URLSearchParams object:

```js harmony
fetch("/form-endpoint", {
  method: "POST",
  headers: {
    "Content-Type": "application/x-www-form-urlencoded",
  },
  body: new URLSearchParams({ username: "user", password: "pass" }),
});
```

**Custom Parsers**: While Express provides built-in body parsers for JSON and URL-encoded data, you might receive data in another format. In such cases, you can create custom middleware to parse and shape the data as needed. This middleware should populate `req.body`.

</details>

<details>
<summary>
17.  <b> How do you create a middleware that logs the request method and URL for every request? </b>
</summary>

- In Express.js, middlewares allow you to handle HTTP requests. Here, you will learn how to create a simple logging middleware that records the request method and URL.

**Setting Up the Express App**

First, install Express via npm, and set up your app.js file:

```jsx harmony
const express = require("express");
const app = express();
```

**Creating the Logging Middleware**
Define a logging function that extracts the request method and URL, and then use app.use() to mount it as middleware.

```jsx harmony
// Logging Middleware
const logRequest = (req, res, next) => {
  console.log(`Received ${req.method}  request for: ${req.url}`);
  next(); // Call next to proceed to the next middleware
};

// Mount the middleware for all routes
app.use(logRequest);
```

**Testing the Setup**
Use `app.get()` to handle GET requests, and app.listen() to start the server.

```jsx harmony
// Sample route
app.get("/", (req, res) => {
  res.send("Hello World");
});

// Start the server
app.listen(3000, () => {
  console.log("Server is running on port 3000");
});
```

When you visit `http://localhost:3000/` in your browser and check the server console, you should see the request being logged.

</details>

<details>
<summary>
18.  <b>What are some of the salient features of express? </b>
</summary>

1. **Middlewares**: Set up middlewares in order to respond to HTTP/RESTful Requests.
2. **Routing**: It is possible to defines a routing table in order to perform different HTTP operations.
3. **Templates**: Dynamically renders HTML Pages based on passing arguments to templates.
4. **High Performance**: Express prepare a thin layer, therefore, the performance is adequate.
5. **Database Support**: Express supports RDBMS as well as NoSQL databases.
6. **MVC Support**: Organize the web application into an MVC architecture. Manages everything from routes to rendering view and preforming HTTP request.
</details>

<details>
<summary>
19.  <b>How to get the name parameters in express? </b>
</summary>

This property is an object containing properties mapped to the named route `“parameters”`.
For example, if you have the route /user/:name, then the “name” property is available as req.params.name. This object defaults to {}.

```jsx harmony
// GET /user/tj
req.params.name;
// => "tj"
```

</details>

<details>
<summary>
20.  <b>How to retrieve the get query string parameters using express? </b>
</summary>

The query string is the part that comes after the URL path, and starts with a question mark ?.

```jsx harmony

?height=6&weight=60
//req.query.height - 6
//req.query.weight - 60
```

</details>

<details>
<summary>
21.  <b> How to send a response back using express?</b>
</summary>

we can use any one of these commands

```jsx harmony

function(req, res) {
	res.send('Hello World!')
}
function(req, res) {
	res.end('Hello World!')
}
function(req, res) {
	res.json({title:'Hello World!'})
}
```

</details>

<details>
<summary>
22.  <b> How to set http response status using express? </b>
</summary>

we can either use res.status() or res.sendStatus()

```jsx hrmony
res.status(404).send("File not found");

//if sendStatus we no need to write send method , i will pre send a few inbuilt messages upon using that

res.sendStatus(200);
// === res.status(200).send('OK')

res.sendStatus(403);
// === res.status(403).send('Forbidden')

res.sendStatus(404);
// === res.status(404).send('Not Found')

res.sendStatus(500);
// === res.status(500).send('Internal Server Error')
```

</details>

<details>
<summary>
23.  <b> What are the different http status codes? </b>
</summary>

| Code | Message                         | Description                                                                                                                                                                                                   |
| ---- | ------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 100  | Continue                        | Only a part of the request has been received by the server, but as long as it has not been rejected, the client should continue with the request                                                              |
| 101  | Switching Protocols             | The server switches protocol                                                                                                                                                                                  |
| 200  | OK                              | The request is OK.                                                                                                                                                                                            |
| 201  | Created                         | The request is complete, and a new resource is created                                                                                                                                                        |
| 202  | Accepted                        | The request is accepted for processing, but the processing is not complete                                                                                                                                    |
| 203  | Non-authoritative Information   | The information in the entity header is from a local or third-party copy, not from the original server.                                                                                                       |
| 204  | No Content                      | A status code and a header are given in the response but there is no entity-body in the reply                                                                                                                 |
| 205  | Reset Content                   | The browser should clear the form used for this transaction for additional input                                                                                                                              |
| 206  | Partial Content                 | The server is returning partial data of the size requested. Used in response to a request specifying a Range header. The server must specify the range included in the response with the Content-Range header |
| 300  | Multiple Choices                | A link list. The user can select a link and go to that location. Maximum five addresses                                                                                                                       |
| 301  | Moved Permanently               | The requested page has moved to a new url                                                                                                                                                                     |
| 302  | Found                           | The requested page has moved temporarily to a new url                                                                                                                                                         |
| 303  | See Other                       | The requested page can be found under a different url                                                                                                                                                         |
| 304  | Not Modified                    | This is the response code to an If-Modified-Since or If-None-Match header, where the URL has not been modified since the specified date                                                                       |
| 305  | Use Proxy                       | The requested URL must be accessed through the proxy mentioned in the Location header                                                                                                                         |
| 306  | Unused                          | This code was used in a previous version. It is no longer used, but the code is reserved                                                                                                                      |
| 307  | Temporary Redirect              | The requested page has moved temporarily to a new url                                                                                                                                                         |
| 400  | Bad Request                     | The server did not understand the request                                                                                                                                                                     |
| 401  | Unauthorized                    | The requested page needs a username and a password                                                                                                                                                            |
| 402  | Payment Required                | You can not use this code yet.                                                                                                                                                                                |
| 403  | Forbidden                       | Access is forbidden to the requested page.                                                                                                                                                                    |
| 404  | Not Found                       | The server can not find the requested page.                                                                                                                                                                   |
| 405  | Method Not Allowed              | The method specified in the request is not allowed                                                                                                                                                            |
| 406  | Not Acceptable                  | The server can only generate a response that is not accepted by the client                                                                                                                                    |
| 407  | Proxy Authentication Required   | You must authenticate with a proxy server before this request can be served                                                                                                                                   |
| 408  | Request Timeout                 | The request took longer than the server was prepared to wait                                                                                                                                                  |
| 409  | Conflict                        | The request could not be completed because of a conflict                                                                                                                                                      |
| 410  | Gone                            | The requested page is no longer available                                                                                                                                                                     |
| 411  | Length Required                 | The "Content-Length" is not defined. The server will not accept the request without it .                                                                                                                      |
| 412  | Precondition Failed             | The pre condition given in the request evaluated to false by the server                                                                                                                                       |
| 413  | Request Entity Too Large        | The server will not accept the request, because the request entity is too large.                                                                                                                              |
| 414  | Request-url Too Long            | The server will not accept the request, because the url is too long. Occurs when you convert a "post" request to a "get" request with a long query information                                                |
| 415  | Unsupported Media Type          | The server will not accept the request, because the mediatype is not supported                                                                                                                                |
| 416  | Requested Range Not Satisfiable | The requested byte range is not available and is out of bounds                                                                                                                                                |
| 417  | Expectation Failed              | The expectation given in an Expect request-header field could not be met by this server.                                                                                                                      |
| 500  | Internal Server Error           | The request was not completed. The server met an unexpected condition.                                                                                                                                        |
| 501  | Not Implemented                 | The request was not completed. The server did not support the functionality required.                                                                                                                         |
| 502  | Bad Gateway                     | The request was not completed. The server received an invalid response from the upstream server.                                                                                                              |
| 503  | Service Unavailable             | The request was not completed. The server is temporarily overloading or down.                                                                                                                                 |
| 504  | Gateway Timeout                 | The gateway has timed out.                                                                                                                                                                                    |
| 505  | HTTP Version Not Supported      | The server does not support the "http protocol" version                                                                                                                                                       |

</details>

<details>
<summary>
24.  <b> Mention few properties of request parameter in express? </b>
</summary>
You can access all the HTTP headers using the Request.headers property:

```jsx harmony
app.get("/", (req, res) => {
  console.log(req.headers);
});

app.get("/", (req, res) => {
  req.header("User-Agent");
});
```

</details>

<details>
<summary>
25.  <b> How can you change http header value of a response?</b>
</summary>

You can change any HTTP header value using Response.set():

```jsx harmony
res.set("Content-Type", "text/html");
res.type("json");
// => 'application/json'

res.type("application/json");
// => 'application/json'

res.type("png");
// => image/png:
```

</details>

<details>
<summary>
26.  <b>How to redirect to other pages server-side? </b>
</summary>

Redirects are common in Web Development. You can create a redirect using the Response.redirect() method:

```jsx harmony
res.redirect("/go-there");
//it can be either a url or a path of file
res.redirect(301, "/go-there");
```

</details>

<details>
<summary>
27.  <b> How does routing work in express?</b>
</summary>

Routing is the process of determining what should happen when a URL is called, or also which parts of the application should handle a specific incoming request.

In the Hello World example we used this code

```jsx harmony
app.get("/", function (req, res) {
  /* */
});
//This creates a route that maps accessing the root domain URL / using the HTTP GET method to the response we want to provide.
```

</details>

<details>
<summary>
28.  <b> What are the tasks that a middleware can do?</b>
</summary>

- Middleware functions can perform the following tasks:

1. Execute any code.
2. Make changes to the request and the response objects.
3. End the request-response cycle.
4. Call the next middleware function in the stack.

</details>

<details>
<summary>
29.  <b> What are the different types of middleware? </b>
</summary>

- An Express application can use the following types of middleware:

1. Application-level middleware
2. Router-level middleware
3. Error-handling middleware
4. Built-in middleware
5. Third-party middleware

</details>

<details>
<summary>
30.  <b>How to serve static assests from express? </b>
</summary>

It’s common to have images, CSS and more in a public subfolder, and expose them to the root level:

```jsx harmony
const express = require("express");
const app = express();

app.use(express.static("public"));

app.listen(3000, () => console.log("Server ready"));
```

</details>

<details>
<summary>
31.  <b> How to provide file download using express? </b>
</summary>

Express provides a handy method to transfer a file as attachment: Response.download().

Once a user hits a route that sends a file using this method, browsers will prompt the user for download.

The Response.download() method allows you to send a file attached to the request, and the browser instead of showing it in the page, it will save it to disk.

```jsx harmony
app.get("/", (req, res) => res.download("./file.pdf"));
```

</details>

<details>
<summary>
32.  <b> How to use the Response.cookie() method to manipulate your cookies?</b>
</summary>

Cookies are small pieces of data sent from a website and are stored in user's web browser while user is browsing that website. Every time the user loads that website back, the browser sends that stored data back to website or server, to distinguish user's previous activity.

```jsx harmony
res.cookie('username', 'Adam')

This method accepts a third parameter which contains various options:
res.cookie('username', 'Adam', { domain: '.bangalore.com', path: '/administrator', secure: true })

res.cookie('username', 'Adam', { expires: new Date(Date.now() + 900000), httpOnly: true })

//clear cookie
res.clearCookie('username')

```

The most useful parameters you can set are:

The most useful parameters you can set are:
| Value | Description |
| ----- | ----------- |
| domain | the cookie domain name|
|expires|set the cookie expiration date. If missing, or 0, the cookie is a session cookie|
|httpOnly|set the cookie to be accessible only by the web server. See HttpOnly|
|maxAge|set the expiry time relative to the current time, expressed in milliseconds|
|path|the cookie path. Defaults to /|
|secure|Marks the cookie HTTPS only|
|signed| set the cookie to be signed|
|sameSite|Value of SameSite|

</details>

<details>
<summary>
33.  <b> How to manage sessions using express?</b>
</summary>

We’ll use the express-session module, which is maintained by the Express team.When implemented, every user of you API or website will be assigned a unique session, and this allows you to store the userstate.as by default Express requests are sequential and no request can be linked to each other. There is no way to know if this request comes from a client that already performed a request previously.

```jsx harmony

const express = require('express')
const session = require('express-session')

const app = express()
app.use(session(
'secret': '343ji43j4n3jn4jk3n'
))
```

- All solutions store the session id in a cookie, and keep the data server-side. The client will receive the session id in a cookie, and will send it along with every HTTP request.
- We’ll reference that server-side to associate the session id with the data stored locally.
- Memory is the default, it requires no special setup on your part, it’s the simplest thing but it’s meant only for development purposes.
- The best choice is a memory cache like Redis, for which you need to setup its own infrastructure.
</details>

<details>
<summary>
34.  <b>How to process forms using Express? </b>
</summary>

The form data will be sent in the POST request body.
To extract it, you will use the express.urlencoded() middleware, provided by Express:

```jsx harmony
const express = require("express");
const app = express();

app.use(express.urlencoded());
```

Now you need to create a POST endpoint on the /submit-form route, and any data will be available on Request.body:

```jsx harmony
app.post("/submit-form", (req, res) => {
  const username = req.body.username;
  //...
  res.end();
});
```

</details>

<details>
<summary>
35.  <b> How To Allow Cors In Expressjs Explain With An Example? </b>
</summary>

In order to allow CORS in Express.js, add the following code in server.js:

```jsx harmony
app.all("*", function (req, res, next) {
  res.set("Access-Control-Allow-Origin", "*");
  res.set("Access-Control-Allow-Methods", "GET, POST, DELETE, PUT");
  res.set("Access-Control-Allow-Headers", "X-Requested-With, Content-Type");
  if ("OPTIONS" == req.method) return res.send(200);
  next();
});
```

or you can install a package called cors ,CORS is a node.js package for providing a Connect/Express middleware that can be used to enable CORS with various options.link

```jsx harmony
var express = require("express");
var cors = require("cors");
var app = express();

app.use(cors());
```

</details>

<details>
<summary>
36.  <b> How do you handle form data or JSON data in Express.js?</b>
</summary>

To handle incoming form data or JSON, Express provides built-in middleware `express.urlencoded` and `express.json`.

```jsx harmony
const express = require("express");
const app = express();

// Middleware to parse JSON and form data
app.use(express.json());
app.use(express.urlencoded({ extended: true }));

app.post("/submit", (req, res) => {
  res.send(`Received data: ${req.body.name}`);
});

app.listen(3000, () => {
  console.log("Server running on http://localhost:3000");
});
```

</details>

<details>
<summary>
37.  <b>How do you handle errors in Express.js? </b>
</summary>

Error-handling middleware is used to catch errors and handle them appropriately.

```jsx harmony
const express = require("express");
const app = express();

app.get("/", (req, res, next) => {
  // Simulate an error
  const err = new Error("Something went wrong!");
  next(err);
});

// Error handling middleware
app.use((err, req, res, next) => {
  console.error(err.message);
  res.status(500).send("Server Error");
});

app.listen(3000, () => {
  console.log("Server running on http://localhost:3000");
});
```

</details>

<details>
<summary>
38.  <b> How do you handle cookies in Express.js? </b>
</summary>

You can use the cookie-parser middleware to handle cookies.

```jsx harmony
const express = require("express");
const cookieParser = require("cookie-parser");
const app = express();

app.use(cookieParser());

app.get("/set-cookie", (req, res) => {
  res.cookie("user", "John Doe");
  res.send("Cookie has been set");
});

app.get("/get-cookie", (req, res) => {
  res.send(`Cookie Value: ${req.cookies.user}`);
});

app.listen(3000, () => {
  console.log("Server running on http://localhost:3000");
});
```

</details>

## Express Pro Level Interview Questions

<details>
<summary>
39.  <b> How do you implement authentication in Express.js using JWT (JSON Web Tokens) </b>
</summary>

JWT is used to securely transmit information between the client and the server.

```jsx harmony
const express = require("express");
const jwt = require("jsonwebtoken");
const app = express();
const secretKey = "your_secret_key";

app.use(express.json());

// Generate token
app.post("/login", (req, res) => {
  const user = { id: 1, username: "JohnDoe" }; // Dummy user
  const token = jwt.sign(user, secretKey, { expiresIn: "1h" });
  res.json({ token });
});

// Middleware to verify token
const verifyToken = (req, res, next) => {
  const token = req.headers["authorization"];
  if (!token) return res.status(403).send("Token required");
  jwt.verify(token, secretKey, (err, decoded) => {
    if (err) return res.status(403).send("Invalid token");
    req.user = decoded;
    next();
  });
};

// Protected route
app.get("/protected", verifyToken, (req, res) => {
  res.send(`Hello ${req.user.username}, welcome to the protected route!`);
});

app.listen(3000, () => {
  console.log("Server running on http://localhost:3000");
});
```

</details>

<details>
<summary>
40.  <b>How do you optimize performance in an Express.js application? </b>
</summary>

- Performance optimization techniques include:

**Using GZIP compression** (compression middleware)
**Caching responses**
**Using asynchronous and non-blocking functions**
**Reducing the number of middleware layers**
**Example of GZIP compression:**

```jsx harmony
const express = require("express");
const compression = require("compression");
const app = express();

app.use(compression()); // Enable GZIP compression

app.get("/", (req, res) => {
  res.send("This response is compressed");
});

app.listen(3000, () => {
  console.log("Server running on http://localhost:3000");
});
```

</details>

<details>
<summary>
41.  <b>How do you implement rate limiting in Express.js? </b>
</summary>

You can use the express-rate-limit middleware to limit the number of requests a client can make in a given time window.

```jsx harmony
const express = require("express");
const rateLimit = require("express-rate-limit");
const app = express();

const limiter = rateLimit({
  windowMs: 15 * 60 * 1000, // 15 minutes
  max: 100, // Limit each IP to 100 requests per windowMs
});

app.use(limiter); // Apply rate limiter

app.get("/", (req, res) => {
  res.send("Welcome! Rate limiting is applied.");
});

app.listen(3000, () => {
  console.log("Server running on http://localhost:3000");
});
```

</details>

<details>
<summary>
42.  <b>How do you handle WebSocket integration in an Express app? </b>
</summary>

Use socket.io for WebSocket connections in Express.

```jsx harmony
const http = require("http");
const socketIo = require("socket.io");
const server = http.createServer(app);
const io = socketIo(server);
```

</details>

<details>
<summary>
43.  <b>How do you optimize a heavy-load Express.js application? </b>
</summary>

- Use caching
- CDN
- database optimization
- load balancing
- clustering,
</details>

<details>
<summary>
44.  <b> How do you handle large payloads in Express.js?</b>
</summary>

- Use streaming
- increase payload limits
- implement pagination.

</details>

<details>
<summary>
45.  <b> How do you implement a microservices architecture with Express.js? </b>
</summary>

- Break down the application into small
- independently deployable services communicating via REST or RPC.

</details>

<details>
<summary>
46.  <b> How can you implement socket.io in an Express app to handle real-time updates? </b>
</summary>

Use socket.io in conjunction with Express to enable real-time, bidirectional event-based communication.

</details>

<details>
<summary>
47.  <b> How would you configure SSL in an Express.js application?  </b>
</summary>

Use https module with SSL certificate

```jsx harmony
const https = require("https");
const fs = require("fs");
const server = https.createServer(
  {
    key: fs.readFileSync("key.pem"),
    cert: fs.readFileSync("cert.pem"),
  },
  app
);
```

</details>

<details>
<summary>
48.  <b>  Explain middleware chaining in Express.js and its performance implications</b>
</summary>

Middleware chaining involves calling multiple middlewares in sequence; however, too many can slow down the app.

</details>

<details>
<summary>
49.  <b> How do you handle transaction management in Express with MongoDB? </b>
</summary>

Use session.startTransaction() in MongoDB to manage transactions.

</details>

<details>
<summary>
50.  <b>How do you handle multi-tenancy in an Express app </b>
</summary>

Implement multi-tenancy by structuring routes, separating databases, or using tenant identifiers.

</details>

<details>
<summary>
51.  <b>  How do you ensure security best practices in an Express.js app?</b>
</summary>

Use Helmet, sanitize inputs, secure headers, implement CORS, and rate limit.

</details>

<details>
<summary>
52.  <b> How can you handle reverse proxying in Express? </b>
</summary>

Use a reverse proxy like Nginx or set up reverse proxy headers `(X-Forwarded-*).`

</details>

<details>
<summary>
53.  <b> How do you create custom error classes in Express? </b>
</summary>

Create custom error classes by extending the Error class.

</details>

<details>
<summary>
54.  <b> How do you handle pagination and sorting in an Express API? </b>
</summary>

Create custom error classes by extending the Error class.

Pass `limit`, `offset`, and `sort` parameters in the request and implement them in the query.

</details>

<details>
<summary>
55.  <b> How do you enable gzip compression in Express? </b>
</summary>

Use the `compression` middleware to enable `gzip` compression.

</details>

<details>
<summary>
56.  <b>Explain how you would test an Express.js API. </b>
</summary>

Use `mocha`, `chai`, and `supertest` to write unit and integration tests for the API.

</details>

<details>
<summary>
57.  <b> </b>
</summary>
</details>

<details>
<summary>
58.  <b> </b>
</summary>
</details>

<details>
<summary>
59.  <b> </b>
</summary>
</details>

<details>
<summary>
60.  <b> </b>
</summary>
</details>

<details>
<summary>
61.  <b> </b>
</summary>
</details>

<details>
<summary>
62.  <b> </b>
</summary>
</details>

<details>
<summary>
63.  <b> </b>
</summary>
</details>

<details>
<summary>
64.  <b> </b>
</summary>
</details>

<details>
<summary>
65.  <b> </b>
</summary>
</details>

<details>
<summary>
66.  <b> </b>
</summary>
</details>

<details>
<summary>
67.  <b> </b>
</summary>
</details>

<details>
<summary>
68.  <b> </b>
</summary>
</details>

<details>
<summary>
69.  <b> </b>
</summary>
</details>

<details>
<summary>
70.  <b> </b>
</summary>
</details>

<details>
<summary>
71.  <b> </b>
</summary>
</details>

<details>
<summary>
72.  <b> </b>
</summary>
</details>
