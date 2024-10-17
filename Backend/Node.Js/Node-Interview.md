# Node Interview Questions Answer

## Basic Questions

<details>
<summary>
1.  <b> What is Node.js?</b>
</summary>

**Node.js** is an open-source, cross-platform JavaScript runtime environment that executes code outside of a web browser. It is built on V8, the same JavaScript engine within Chrome, and optimized for high performance. This environment, coupled with an event-driven, non-blocking I/O framework, is tailored for server-side web development and more.

### Key Features

- **Asynchronous & Non-Blocking**: Ideal for handling a myriad of concurrent connections with efficiency.
- **V8 Engine**: Powered by Google's V8, Node.js boasts top-tier JavaScript execution.
- **Libuv Library**: Ensures consistent performance across platforms and assists in managing I/O operations.
- **NPM**: A vast package ecosystem simplifies module management and deployment.
- **Full-Stack JavaScript**: Allows for unified server and client-side code in JavaScript.

### Use Cases

- **Data Streaming**: Suited for real-time streaming of audio, video, and lightweight data.
- **API Servers**: Ideal for building fast, scalable, and data-intensive applications.
- **Microservices**: Its module-oriented design facilitates the development of decoupled, independently scalable services.
- **Single Page Applications**: Often used with frameworks like Angular, React, or Vue to craft robust, server-side backends.
- **Chat Applications**: Its real-time capabilities are advantageous in building instant messaging systems.
- **Internet of Things (IoT)**: Provides a lightweight environment for running applications on constrained devices like Raspberry Pi.
</details>

<details>
<summary>
2.  <b> Why Node.js?</b>
</summary>

- **Unified Language**: Utilizing JavaScript both on the frontend and backend brings coherence to development efforts, potentially reducing debugging time and enabling shared libraries.
- **NPM Ecosystem**: The NPM repository offers myriad open-source packages, empowering rapid development and feature expansion.
- **Rapid Prototyping**: Express, a minimalist web framework for Node.js, and NPM's wealth of modules expedite early application development and testing.
- **Scalability**: Cluster modules, load balancers, and Microservice Architecture aid in linear, on-demand scaling for both simple and intricate applications.
- **Real-Time Power**: With built-in WebSockets and event-based architecture, Node.js excels in constructing real-time applications such as multiplayer games, stock trading platforms, and chat applications.
- **Open Source**: Being an open-source technology, Node.js continuously benefits from community contributions, updates, and enhanced packages.
</details>

<details>
<summary>
3.  <b> What is the role of package.json in a Node.js project? </b>
</summary>

`package.json` is a file that contains metadata about the project and its dependencies.
It helps manage the project’s dependencies, scripts, version, and other configurations.

```jsx harmony

{
  "name": "my-project",
  "version": "1.0.0",
  "scripts": {
    "start": "node app.js",
    "test": "jest"
  },
  "dependencies": {
    "express": "^4.17.1"
  },
  "devDependencies": {
    "jest": "^27.0.6"
  }
}

```

</details>

<details>
<summary>
4.  <b>  Explain Event-Driven Architecture in Node.js.</b>
</summary>
Node.js uses an event-driven, non-blocking I/O model.  The server listens for events and uses callbacks to handle asynchronous operations, making it efficient for I/O-heavy operations.

```jsx harmony
const EventEmitter = require("events");
const eventEmitter = new EventEmitter();

eventEmitter.on("start", () => {
  console.log("Started event triggered");
});

eventEmitter.emit("start");
```

</details>

<details>
<summary>
5.  <b>Describe the event-driven programming in Node.js.</b>
</summary>

**Event-driven programming,** a hallmark of Node.js, uses an **event, listener,** and **emitter** architecture to handle asynchronous tasks. This design centers around events and how they trigger actions in the attached listeners.

**Core Components**

1. **Event Emitter**: Acts as the event registry and dispatcher, letting objects register interest in particular events and emit these events when they occur.
2. **Event Handler (Listener)**: Associates with a particular event through registration. These callback functions will be asynchronously carried out when a matching event is emitted.

**Event Emitter and Handlers**

```jsx harmony
const { EventEmitter } = require("events");
const emitter = new EventEmitter();

emitter.on("event-name", (eventArgs) => {
  console.log(`Event-name was emitted with arguments: ${eventArgs}`);
});

emitter.emit("event-name", "Some Payload");
```

In this code, when `emit` is called, the `on` method's callback is executed asynchronously.

**Event Loop in Node.js**

1. **Call Stack**: Maintains the call order of the functions and methods being executed.

2. **Node APIs** and **Callbacks Queue**: Handle I/O tasks and timers.

3. **Event Loop**: Constantly watches the execution stack and checks whether it's clear to execute pending tasks from the Callback Queue.

**Applications in Node.js**

1. **HTTP Server**: Listens for and serves requests.
2. **File System Operations**: Execute I/O tasks.
3. **Database Operations**: Such as data retrieval.

</details>

<details>
<summary>
6.  <b>  What is the event loop in Node.js? </b>
</summary>

The **event loop** is a fundamental concept in Node.js for managing asynchronous operations. Its efficiency is a key reason behind Node.js's high performance.

**How Does the Event Loop Work?**

1. **Initialization**: When Node.js starts, it initializes the **event loop** to watch for I/O operations and other asynchronous tasks.

2. **Queueing**: Any task or I/O operation is added to a **queue**, which can be either the `microtask queue` or the `macrotask/Callback queue`.

3. **Polling**: The event loop iteratively checks for tasks in the queue while also **waiting** for I/O and timers.

4. **Execution Phases**: When the event loop detects tasks in the queue, it executes them in specific phases, ensuring order efficiency.

**Task Scheduler Zones: microtask and Callback Queue**

1. **Microtask Queue**: This is a highly prioritized queue, usually acting over tasks in the **Callback Queue**. Useful for tasks that require immediate attention.
2. **Callback Queue (Macrotask Queue)**: Also known as the 'Task Queue,' it manages events and I/O operations.

**Event Loop Phases**

- **Timers**: Manages timer events for scheduled tasks.
- **Pending callbacks**: Handles system events such as I/O, which are typically queued by the kernel.
- **Idle / prepare**: Ensures internal actions are managed before I/O events handling.
- **Poll**: Retrieves New I/O events.
- **Check**: Executes 'setImmediate' functions.
- **Close**: Handles close events, such as 'socket.close'.

**Task Scheduling: microtasks and macrotasks**

1.  **Microtasks (process.nextTick and Promises)**: Executed after each task.
2.  **Macrotasks**: Executed after the poll phase when the event loop is not behind any file I/O or scheduled time. This includes timers, setImmediate, and I/O events.

**Timers and Task Queues**

**Node.js**

```js
// Code Example
console.log("Start");

setTimeout(() => {
  console.log("Set Timeout - 1");

  Promise.resolve()
    .then(() => {
      console.log("Promise - 1");
    })
    .then(() => {
      console.log("Promise - 2");
    });
}, 0);

setImmediate(() => {
  console.log("Set Immediate");
});

process.nextTick(() => {
  console.log("Next Tick");
  // It's like an infinite loop point for microtask queue
  process.nextTick(() => console.log("Next Tick - nested"));
});

fs.readFile(file, "utf-8", (err, data) => {
  if (err) throw err;
  console.log("File Read");
});

console.log("End");
```

</details>

<details>
<summary>
7.  <b> Explain what "non-blocking" means in Node.js. </b>
</summary>

**Node.js leverages non-blocking I/O** to handle multiple operations without waiting for each to complete separately.

This particular I/O model, coupled with the event-driven paradigm of Node.js, is key to its high performance and scalability, making it **ideal** for tasks such as data streaming, background tasks, and concurrent operations.

**Non-Blocking I/O**

With non-blocking I/O, an application **doesn't halt** or wait for a resource to become available. Instead, it goes on executing other tasks that don't depend on that resource.

For instance, if a file operation is in progress, Node.js doesn't pause the entire application until the file is read or written. This allows for a more responsive and efficient system, especially when handling multiple, concurrent I/O operations.

**Event Loop**

Node.js constantly monitors tasks and I/O operations. When a task or operation is ready, it triggers an event. This mechanism is referred to as the **event loop**.

When an event fires, a corresponding event handler or callback function is executed.

**Concurrency Without Threads**

Traditionally, concurrency can be achieved in languages that support multithreading (e.g., Java). However, managing and coordinating multiple threads can be challenging and is a common source of bugs.

Node.js, on the other hand, provides a simplified yet effective concurrency model using non-blocking I/O and the event loop. It achieves parallelism through mechanisms such as **callbacks**, **Promises**, and **async/await**.

By not using threads, Node.js eliminates many of the complexities associated with traditional multithreaded architectures, making it easier to **develop** and **maintain** applications, particularly those requiring high concurrency.

**Code Example: File I/O**

Here is the JavaScript code:

```javascript
const fs = require("fs");

// Perform non-blocking file read operation
fs.readFile("path/to/file", (err, data) => {
  if (err) throw err;
  console.log(data);
});

// Other non-blocking operations continue without waiting for file read
console.log("This message is displayed immediately.");
```

In this example, the file read operation is non-blocking. Node.js does not halt the thread of execution to wait for the file read to complete. Instead, the supplied callback function is invoked when the read operation finishes.
<br>

</details>

<details>
<summary>
8.  <b> What is "npm" and what is it used for?</b>
</summary>

**npm (Node Package Manager)** is a powerful and highly popular package manager that is focused on the Node.js environment. Its primary purpose is to simplify the installation, management, and sharing of libraries or tools written in Node.js.

npm is more than just a package manager: It's also a thriving ecosystem, offering a plethora of ready-to-use modules and tools, thereby making the development workflow for Node.js even more efficient.

**Key Functions**

- **Package Installation**: npm makes it easy to install and specify dependencies for Node.js applications. Developers can simply define required packages in a `package.json` file, and npm resolves and installs all dependencies.

- **Dependency Management**: npm establishes a tiered dependency system, effectively managing the versions and interdependencies of various packages.

- **Registry Access**: It acts as a central repository for Node.js packages, where developers can host, discover, and access modules.

- **Version Control**: npm enables version control to ensure consistent and predictable package installations. It supports features such as semantic versioning and lock files.

- **Lifecycle Scripts**: It allows developers to define custom scripts for tasks like application start or build, making it convenient to execute routine operations.

- **Packaging and Publication**: Developers can use npm to bundle their applications and publish them, ready for use by others.

**npm Client and Registry**

- The **npm client** is the command-line tool that developers interact with locally. It provides a set of commands to manage a project's packages, scripts, and configuration.

- The **npm registry** is a global, central database of published Node.js packages. It's where modules and libraries are made available to the Node.js community. The official, public registry is managed by npm, Inc.

**npm vs yarn**

- **yarn** is another popular package manager, introduced by Facebook. Like npm, it's designed for Node.js and excels in areas like performance and determinism. However, both npm and yarn are continuously evolving, and their differences are becoming more nuanced.

**Common Commands**

1. **install**: This command downloads and installs the specified packages and their dependencies.
2. **init**: This command initializes a `package.json` file for the project.
3. **start**: This command typically begins the execution of a Node.js application, as specified in the `scripts` section of `package.json`.
4. **publish**: This command is used to publish the package to the npm registry.

**npm Scripts**

One of the key features of npm is the ability to define scripts in the `package.json` file, executing them with the `npm run` command. This allows for automation of tasks such as testing, building, and starting the application.

These scripts have access to a variety of built-in and environment-specific variables, helping you to customize the script's behavior.

**example**

In `package.json`:

```json
{
  "scripts": {
    "start": "node server.js"
  }
}
```

You can then execute:

```jsx harmony
npm start
```

to start the server.

**npm Web Interface**

While most developers interact with npm via the command line, it also offers a web interface called `npmjs.com`. The website allows users to search for packages, view documentation, and explore related modules. It is also where developers publish and manage their packages.

</details>

<details>
<summary>
9.  <b> How do you manage packages in a Node.js project? </b>
</summary>

**Node.js** utilizes **npm** (Node Package Manager) or yarn for **package management**.

**npm vs. Yarn**

Both tools create a `node_modules` folder, but they have subtle differences:

- **Yarn's** `yarn.lock` provides deterministic package versions, while npm uses `package-lock.json`.
- npm uses `npm install` while Yarn uses `yarn add` to install a package.

Yarn also has advanced features like parallel package installations and a lockfile ensuring consistent installations across machines.

**Core npm Commands**

1. **npm init**: Initializes a new project and creates a `package.json` file.
2. **npm install [package] (-D)**: Installs a package and updates the `package.json` file. The `-D` flag indicates a devDependency.
3. **npm update [package]**: Updates installed packages to their latest versions.

**Using npm Scripts**

The `package.json` can include custom scripts for tasks like testing, building, and deployment, opening up the terminal from the current project directory and running `npm run SCRIPT_NAME`.

**CLI Examples**

- **Install express**: `npm install express`
- **Install express and save as a devDependency**: `npm install express --save-dev`
- **Update all packages**: `npm update`

</details>

<details>
<summary>
10.  <b> Describe some of the core modules of Node.js. </b>
</summary>

**Node.js** offers a host of inbuilt modules that cover diverse functionalities, ranging from file system handling to HTTP server management.
These modules expedite development and allow for more streamlined application building.

**Core Modules Overview**

**Major Categories**

1. **Basic/System Control**: Modules optimized for system interaction, diagnostics, and error handling.
2. **File System Handling**: Offers a range of file operations.
3. **Networking**: Specialized for data communication over various network protocols.
4. **Utility Modules**: Miscellaneous tools for data analysis, task scheduling, etc.

**Key Modules**

**Basic/System Control**

1. **`os`**: Provides system-related utility functions. Example: `os.freemem()`, `os.totalmem()`.
2. **`util`**: General utility functions primarily used for debugging. Example: `util.inspect()`.

**File System Handling**

- **`fs`**: Offers extensive file system capabilities. Commonly used methods include `fs.readFile()` and `fs.writeFile()`.

**Networking**

- **`http`/`https`**: Implements web server and client. Example: `http.createServer()`.
- **`net`**: Facilitates low-level networking tasks. Example: `net.createServer()`.
- **`dgram`**: Delivers UDP Datagram Socket support for messaging.

**Utility Modules**

1. **`crypto`**: Encompasses cryptographic operations. Common methods include `crypto.createHash()` and `crypto.createHmac()`.
2. **`zlib`**: Offers data compression capabilities integrated with various modules like `http`.
3. **`stream`**: Facilitates event-based data stream processing.

**Others**

1.  **`path`**: Aids in file path string manipulation.
2.  **`url`**: Parses and formats URL strings, especially beneficial in web applications and server operations.

**Code Example: Using Core Modules**

Here is the node.js code:

```js
const os = require("os");
const fs = require("fs");
const http = require("http");
const path = require("path");
const url = require("url");
const zlib = require("zlib");

// Module: os
console.log("Free memory:", os.freemem());
console.log("Total memory:", os.totalmem());

// Module: fs
fs.readFile("input.txt", "utf8", (err, data) => {
  if (err) throw err;
  console.log(data);
});

// Module: http
http
  .createServer((req, res) => {
    const reqPath = url.parse(req.url).pathname;
    const file = path.join(__dirname, reqPath);

    const readStream = fs.createReadStream(file);
    readStream.pipe(zlib.createGzip()).pipe(res);
  })
  .listen(8080);
```

</details>

<details>
<summary>
11.  <b> How do you create a simple server in Node.js using the HTTP module? </b>
</summary>

Let's look at how to create a simple server in Node.js using the built-in `http` module.

### Server Setup

First, a few steps are necessary.

1. **Import the Module**: Use `require` to load the `http` module.
2. **Define Callback Function**: For each request, the server will execute a specific callback function. This function takes two parameters:

   - `request`: Represents the HTTP request, from which you can extract any necessary data.
   - `response`: Use this parameter to define what the server sends back to the client.

3. **Server Initialization**: Use the `http.createServer` method to set up the server and define the callback function.
4. **Listen on a Port**: Use the `.listen` method to specify the port the server should "listen" on, waiting for incoming requests.

**Server Setup**

Here is the Node.js code:

```js
// Import the http module
const http = require("http");

// Define the callback function
const requestListener = (req, res) => {
  res.writeHead(200);
  res.end("Hello, World!");
};

// Server initialization
const server = http.createServer(requestListener);

// Listen on port 8080
server.listen(8080);
```

**Request Handler**

The **Request listener** is the main entry to the server. This callback function handles the incoming client request and sends a response back to the client.

The [`req`](https://nodejs.org/api/http.html#http_class_http_incomingmessage) object represents the HTTP request that the server receives. It provides all the details about the request, such as the request URL, request headers, request method, and more.

The `res` object is the server's response to the client. You can use methods on this object, like `res.write()` and `res.end()`, to send data back to the client. In most cases, you'll use `res.end()` to send a response.

**Request Listener with More Capabilities**

Here is the Node.js code:

```js
const requestListener = (req, res) => {
  if (req.url === "/profile") {
    res.writeHead(200);
    res.end("Welcome to your profile!");
  } else {
    res.writeHead(200);
    res.end("Hello, World!");
  }
};
```

In this example, we're checking the request URL. If it's `/profile`, the server will respond with a "Welcome!" message; otherwise, it will respond with "Hello, World!".

This server is basic yet powerful. With this foundational understanding, you can extend the server's behavior in numerous ways, such as by serving dynamic content or handling different HTTP methods like `POST` and `PUT`.
<br>

</details>

<details>
<summary>
12.  <b> Explain the purpose of the File System (fs) module. </b>
</summary>

The **File System (fs)** module in Node.js facilitates file operations such as reading, writing, and manipulation. It's a core module, meaning it's available without needing 3rd-party installations.

**Key Methods of the `fs` Module**

- **Asynchronous Methods**: Ideal for non-blocking file I/O operations. Their function names end with `File`.
- **Synchronous Methods**: Best suited for simpler scripts and robustness is needed.
- **File Names**: As a convention, file and folder names in the Node.js `fs` module that correspond to methods end with `Sync` to indicate synchronous operations (e.g., `renameSync`).

**The Synchronous Approach**

Though the synchronous file methods can make scripting simpler, their use should be limited in web servers as they can block the event loop, reducing scalability and performance.

Synchronous operations in Node's `fs` module are best avoided in server-side applications that must manage many connections.

**Supported Operations**

The `fs` module covers a wide array of file-handling tasks, including:

1. **I/O Operations**: Read or write files using streams or high-level functions.
2. **File Metadata**: Obtain attributes such as size or timestamps.
3. **Directories**: Manage folders and the files within them, including sync and async variants for listing.
4. **File Types**: Distinguish between files and directories.
5. **Links**: Create and manage hard or symbolic links.
6. **Permissions and Ownership**: Integrate with operating systems' security systems.

**File Reading**

Here is the Node.js code:

```javascript
const fs = require("fs");

// Asynchronous read
fs.readFile("input.txt", (err, data) => {
  if (err) {
    return console.error(err);
  }
  console.log("Asynchronous read: " + data.toString());
});

// Synchronous read
const data = fs.readFileSync("input.txt");
console.log("Synchronous read: " + data.toString());
```

In the above code, both asynchronous and synchronous methods are demonstrated for file reading.

**Considerations for the Web**

When working with HTTP connections or in web applications, the **synchronous methods may block other requests**.
Always favor their asynchronous counterparts, especially in web applications.

</details>

<details>
<summary>
13.  <b> What is the Buffer class in Node.js? </b>
</summary>

In **Node.js**, the `Buffer` class is a core module that provides a way to **read**,
**manipulate**, and **allocate** binary data, which primarily represents a sequence of bytes (octets).

**Key Features**

- **Backbone of I/O Operations**: Buffers serve as the primary data structure for handling I/O in Node.js, acting as a transient container for data being read from or written to streams and files.
- **Raw Binary Data**: Buffers are used for handling raw binary data, which is particularly useful for tasks like cryptography, network protocols, and WebGL operations.
- **Unmodifiable Size**: Buffers are fixed in size after allocation. To resize a buffer, you'd need to create a new buffer with the necessary size and optionally copy over the original data.
- **Shared Memory**: Buffers provide a mechanism for sharing memory between Node.js instances or between Node.js and C++ Addons, offering enhanced performance in certain scenarios.

**Common Use Cases**

- **File and Network Operations**: Buffers are leveraged for reading and writing data from files, sockets, and other sources/sinks.
- **Data Conversion**: For example, converting text to binary data or vice versa using character encodings such as UTF-8.
- **Binary Calculations**: Buffers make binary manipulations more manageable, such as computing checksums or parsing binary file formats.

**Buffer Use**

Here is the JavaScript code:

```javascript
let bufTemp = Buffer.from("Hey!");
console.log(bufTemp.toString()); // Output: Hey!

let bufAlloc = Buffer.alloc(5, "a");
console.log(bufAlloc.toString()); // Output: aaaaa

bufAlloc.write("Hello");
console.log(bufAlloc.toString()); // Output: Hello

let bufSlice = bufAlloc.slice(0, 3); // Slice the buffer
console.log(bufSlice.toString()); // Output: Hel
```

</details>

<details>
<summary>
14.  <b> What are streams in Node.js and what types are available? </b>
</summary>

**Node.js** utilizes **streams** for efficient handling of input/output data, offering two main varieties: readable and writable.

**Categories of Streams**

1. **Standard Streams**: Represent standard input, output, and error. These are instances of Readable or Writable streams.

2. **Duplex Streams**: Facilitate both reading and writing. They can be connected to processes or handling pipelines.

3. **Transform Streams**: A special type that acts as an intermediary, modifying the data as it passes through.

**Practical Implementations**

- **HTTP Transactions**: HTTP clients use readable and writable streams for sending requests and receiving responses. HTTP servers also apply these streams for similar actions in the opposite direction.

- **File System**: Reading and writing files in Node.js utilizes these streams. For instance, the `fs.createReadStream()` method generates a readable stream whereas `fs.createWriteStream()` creates a writable one.

**Workflows**

1. **Standard I/O Streams**: These support interactivity between a program and its running environment. For example, stdout (a writable stream) can be used to display information, and stdin (a readable stream) can capture user input.

2. **File Operations**: Streams are beneficial when working with large files. This is because they streamline the process by breaking it down into smaller, manageable chunks, thereby conserving memory.

3. **Server Operations**: Streams facilitate data transfer for operations such as network requests, database communications, and more.

4. **Pipelines**: Streams can be easily combined using `pipe()` to create powerful, efficient operations called pipelines. For instance, to compress a file and then write it to disk, you can pipe a readable stream to a transform stream and then to a writable stream. This arrangement neatly dictates the flow of data.
<br>
</details>

## Advanced Questions

<details>
<summary>
15.  <b> What is V8? </b>
</summary>

The `V8` library provides Node.js with a JavaScript engine (a program that converts Javascript code into lower level or machine code that microprocessors can understand), which Node.js controls via the V8 C++ API. V8 is maintained by Google, for use in Chrome.

**The Chrome V8 engine :**

1. The V8 engine is written in C++ and used in Chrome and Nodejs.
2. It implements ECMAScript as specified in ECMA-262.
3. The V8 engine can run standalone we can embed it with our own C++ program.
</details>

<details>
<summary>
16.  <b>What is libuv? </b>
</summary>

`libuv` is a C library that is used to abstract non-blocking I/O operations to a consistent interface across all supported platforms. It provides mechanisms to handle file system, DNS, network, child processes, pipes, signal handling, polling and streaming. It also includes a thread pool for offloading work for some things that can't be done asynchronously at the operating system level.

</details>

<details>
<summary>
17.  <b> What is the difference between returning a callback and just calling a callback? </b>
</summary>

```jsx harmony
return callback();
//some more lines of code; -  won't be executed

callback();
//some more lines of code; - will be executed
```

Of course returning will help the context calling async function get the value returned by callback.

```jsx harmony
function do2(callback) {
  log.trace("Execute function: do2");
  return callback("do2 callback param");
}

var do2Result = do2((param) => {
  log.trace(`print ${param}`);
  return `return from callback(${param})`; // we could use that return
});

log.trace(`print ${do2Result}`);
```

**Output**

[0] Execute function: do2
[0] print do2 callback param
[0] print return from callback(do2 callback param)

</details>

<details>
<summary>
18.  <b> What is an error-first callback? </b>
</summary>

`Error-first callbacks` are used to pass errors and data. The first argument is always an error object that the programmer has to check if something went wrong. Additional arguments are used to pass data.

```jsx harmony
fs.readFile(filePath, function (err, data) {
  if (err) {
    //handle the error
  }
  // use the data object
});
```

</details>

<details>
<summary>
19.  <b>  What's the difference between operational and programmer errors? </b>
</summary>

Operation errors are not bugs, but problems with the system, like request timeout or hardware failure. On the other hand programmer errors are actual bugs.

</details>

<details>
<summary>
20.  <b> What is the difference between Nodejs, AJAX, and jQuery?</b>
</summary>

The one common trait between Node.js, AJAX, and jQuery is that all of them are the advanced implementation of JavaScript.
However, they serve completely different purposes.

- Node.js –It is a server-side platform for developing client-server applications. For example, if we’ve to build an online employee management system, then we won’t do it using client-side JS. But the Node.js can certainly do it as it runs on a server similar to Apache, Django not in a browser.

- AJAX (aka Asynchronous Javascript and XML) –It is a client-side scripting technique, primarily designed for rendering the contents of a page without refreshing it. There are a no. of large companies utilizing AJAX such as Facebook and Stack Overflow to display dynamic content.

- jQuery –It is a famous JavaScript module which complements AJAX, DOM traversal, looping and so on. This library provides many useful functions to help in JavaScript development. However, it’s not mandatory to use it but as it also manages cross-browser compatibility, so can help you produce highly maintainable web applications.
</details>

<details>
<summary>
21.  <b> How to make Post request in Node.js? </b>
</summary>

```jsx harmony
var request = require("request");
request.post(
  "http://localhost:8000/add/action",
  {
    form: {
      key: "value",
    },
  },
  function (error, response, body) {
    if (!error && response.statusCode == 200) {
      console.log(body);
    }
  }
);
```

</details>

<details>
<summary>
22.  <b> What are the key features of Node.js?  </b>
</summary>

1. **Asynchronous event driven IO helps concurrent request handling** – All APIs of Node.js are asynchronous. This feature means that if a Node receives a request for some Input/Output operation, it will execute that operation in the background and continue with the processing of other requests. Thus it will not wait for the response from the previous requests.
2. **Fast in Code execution** – Node.js uses the V8 JavaScript Runtime engine, the one which is used by Google Chrome. Node has a wrapper over the JavaScript engine which makes the runtime engine much faster and hence processing of requests within Node.js also become faster.
3. **Single Threaded but Highly Scalable** – Node.js uses a single thread model for event looping. The response from these events may or may not reach the server immediately. However, this does not block other operations. Thus making Node.js highly scalable. Traditional servers create limited threads to handle requests while Node.js creates a single thread that provides service to much larger numbers of such requests.
4. **Node.js library uses JavaScript** – This is another important aspect of Node.js from the developer’s point of view. The majority of developers are already well-versed in JavaScript. Hence, development in Node.js becomes easier for a developer who knows JavaScript.
5. **There is an Active and vibrant community for the Node.js framework** – The active community always keeps the framework updated with the latest trends in the web development.
6. **No Buffering** – Node.js applications never buffer any data. They simply output the data in chunks.
</details>

<details>
<summary>
23.  <b>What is control flow function? </b>
</summary>

It is a generic piece of code which runs in between several asynchronous function calls is known as control flow function.

</details>

<details>
<summary>
24.  <b>What are Event Listeners? </b>
</summary>

`Event Listeners` are similar to call back functions but are associated with some event. For example when a server listens to http request on a given port a event will be generated and to specify http server has received and will invoke corresponding event listener. Basically, Event listener's are also call backs for a corresponding event.

Node.js has built in event's and built in event listeners. Node.js also provides functionality to create Custom events and Custom Event listeners.

</details>

<details>
<summary>
25.  <b>  If Node.js is single threaded then how it handles concurrency?</b>
</summary>

Node provides a single thread to programmers so that code can be written easily and without bottleneck. Node internally uses multiple POSIX threads for various I/O operations such as File, DNS, Network calls etc.

When Node gets I/O request it creates or uses a thread to perform that I/O operation and once the operation is done, it pushes the result to the event queue. On each such event, event loop runs and checks the queue and if the execution stack of Node is empty then it adds the queue result to execution stack.

This is how Node manages concurrency.

</details>

<details>
<summary>
26.  <b> What is Callback Hell? </b>
</summary>

The asynchronous function requires callbacks as a return parameter. When multiple asynchronous functions are chained together then callback hell situation comes up.

</details>

<details>
<summary>
27.  <b> Could we run an external process with Node.js? </b>
</summary>

Yes. Child process module enables us to access operating system functionaries or other apps. Scalability is baked into Node and child processes are the key factors to scale our application. You can use child process to run system commands, read large files without blocking event loop, decompose the application into various “nodes” (That’s why it’s called Node).

Child process module has following three major ways to create child processes –

1. spawn - child_process.spawn launches a new process with a given command.
2. exec - child_process.exec method runs a command in a shell/console and buffers the output.
3. fork - The child_process.fork method is a special case of the spawn() to create child processes.
</details>

<details>
<summary>
28.  <b> List out the differences between AngularJS and NodeJS? </b>
</summary>

AngularJS is a web application development framework. It’s a JavaScript and it is different from other web app frameworks written in JavaScript like jQuery. NodeJS is a runtime environment used for building server-side applications while AngularJS is a JavaScript framework mainly useful in building/developing client-side part of applications which run inside a web browser.

</details>

<details>
<summary>
29.  <b>How you can monitor a file for modifications in Node.js </b>
</summary>

We can take advantage of File System watch() function which watches the changes of the file.

</details>

<details>
<summary>
30.  <b> What are the core modules of Node,js? </b>
</summary>

1. EventEmitter
2. Stream
3. FS
4. Net
5. Global Objects

</details>

<details>
<summary>
31.  <b> What is REPL in context of Node? </b>
</summary>

`REPL` stands for Read Eval Print Loop and it represents a computer environment like a window console or unix/linux shell where a command is entered and system responds with an output. Node.js or Node comes bundled with a REPL environment. It performs the following desired tasks.

- Read - Reads user's input, parse the input into JavaScript data-structure and stores in memory.
- Eval - Takes and evaluates the data structure
- Print - Prints the result
- Loop - Loops the above command until user press ctrl-c twice.
</details>

<details>
<summary>
32.  <b> What is Callback? </b>
</summary>

`Callback` is an asynchronous equivalent for a function. A callback function is called at the completion of a given task. Node makes heavy use of callbacks. All APIs of Node are written is such a way that they supports callbacks.

For example, a function to read a file may start reading file and return the control to execution environment immediately so that next instruction can be executed. Once file I/O is complete, it will call the callback function while passing the callback function, the content of the file as parameter. So there is no blocking or wait for File I/O.

This makes Node.js highly scalable, as it can process high number of request without waiting for any function to return result.

</details>

<details>
<summary>
33.  <b> What is a blocking code? </b>
</summary>

If application has to wait for some I/O operation in order to complete its execution any further then the code responsible for waiting is known as blocking code.

</details>

<details>
<summary>
34.  <b>  How Node prevents blocking code? </b>
</summary>

By providing callback function. Callback function gets called whenever corresponding event triggered.

</details>

<details>
<summary>
35.  <b>  What is Event Loop?</b>
</summary>

Node.js is a single threaded application but it support concurrency via concept of event and callbacks. As every API of Node js are asynchronous and being a single thread, it uses async function calls to maintain the concurrency. Node uses observer pattern. Node thread keeps an event loop and whenever any task get completed, it fires the corresponding event which signals the event listener function to get executed.

</details>

<details>
<summary>
36.  <b> What is Event Emmitter?</b>
</summary>

All objects that emit events are members of EventEmitter class. These objects expose an eventEmitter.on() function that allows one or more functions to be attached to named events emitted by the object.

When the EventEmitter object emits an event, all of the functions attached to that specific event are called synchronously.

```jsx harmony
const EventEmitter = require("events");

class MyEmitter extends EventEmitter {}

const myEmitter = new MyEmitter();
myEmitter.on("event", () => {
  console.log("an event occurred!");
});
myEmitter.emit("event");
```

</details>

<details>
<summary>
37.  <b>  What is purpose of Buffer class in Node?</b>
</summary>

`Buffer` class is a global class and can be accessed in application without importing buffer module. A Buffer is a kind of an array of integers and corresponds to a raw memory allocation outside the V8 heap. A Buffer cannot be resized.

</details>

<details>
<summary>
38.  <b>   What is difference between synchronous and asynchronous method of fs module? </b>
</summary>

Every method in `fs` module has synchronous as well as asynchronous form. Asynchronous methods takes a last parameter as completion function callback and first parameter of the callback function is error. It is preferred to use asynchronous method instead of synchronous method as former never block the program execution where the latter one does.

</details>

<details>
<summary>
39.  <b> What are streams? </b>
</summary>

Streams are objects that let you read data from a source or write data to a destination in continuous fashion. In Node.js, there are four types of streams.

- **Readable** - Stream which is used for read operation.
- **Writable** - Stream which is used for write operation.
- **Duplex** - Stream which can be used for both read and write operation.
- **Transform** - A type of duplex stream where the output is computed based on input.
</details>

<details>
<summary>
40.  <b> What is Chaining in Node? </b>
</summary>

`Chanining` is a mechanism to connect output of one stream to another stream and create a chain of multiple stream operations. It is normally used with piping operations.

</details>

<details>
<summary>
41.  <b>  How can you avoid callback hells? </b>
</summary>

- modularization: break callbacks into independent functions
- use Promises
- use yield with Generators and/or Promises
</details>

<details>
<summary>
42.  <b>   How to avoid callback hell in Node.js?</b>
</summary>

Node.js internally uses a single-threaded event loop to process queued events. But this approach may lead to blocking the entire process if there is a task running longer than expected.

Node.js addresses this problem by incorporating callbacks also known as higher-order functions. So whenever a long-running process finishes its execution, it triggers the callback associated.

sometimes, it could lead to complex and unreadable code. More the no. of callbacks, longer the chain of returning callbacks would be.

There are four solutions which can address the callback hell problem.

**Make your program modular**

It proposes to split the logic into smaller modules. And then join them together from the main module to achieve the desired result.

**Use async mechanism**

It is a widely used Node.js module which provides a sequential flow of execution.

The async module has`<async.waterfall>`API which passes data from one operation to other using the next callback.

Another async API `<async.map>` allows iterating over a list of items in parallel and calls back with another list of results.

With the async approach, the caller’s callback gets called only once. The caller here is the main method using the async module.

**Use promises mechanism**

Promises give an alternate way to write async code. They either return the result of execution or the error/exception. Implementing promises requires the use of <.then()> function which waits for the promise object to return. It takes two optional arguments, both functions. Depending on the state of the promise only one of them will get called. The first function call proceeds if the promise gets fulfilled. However, if the promise gets rejected, then the second function will get called.

**Use generators**

Generators are lightweight routines, they make a function wait and resume via the yield keyword. Generator functions uses a special syntax <function\* ()>. They can also suspend and resume asynchronous operations using constructs such as promises or and turn a synchronous code into asynchronous.

</details>

<details>
<summary>
43.  <b> Explain how does Node.js work? </b>
</summary>

A Node.js application creates a single thread on its invocation. Whenever Node.js receives a request, it first completes its processing before moving on to the next request.

Node.js works asynchronously by using the event loop and callback functions, to handle multiple requests coming in parallel. An Event Loop is a functionality which handles and processes all your external events and just converts them to a callback function. It invokes all the event handlers at a proper time. Thus, lots of work is done on the back-end, while processing a single request, so that the new incoming request doesn’t have to wait if the processing is not complete.

While processing a request, Node.js attaches a callback function to it and moves it to the back-end. Now, whenever its response is ready, an event is called which triggers the associated callback function to send this response.

</details>

<details>
<summary>
44.  <b> When should we use Node.js? </b>
</summary>

`Node.js` is well suited for applications that have a lot of concurrent connections and each request only needs very few CPU cycles, because the event loop (with all the other clients) is blocked during execution of a function. I believe Node.js is best suited for real-time applications: online games, collaboration tools, chat rooms, or anything where what one user (or robot? or sensor?) does with the application needs to be seen by other users immediately, without a page refresh.

</details>

<details>
<summary>
45.  <b> How does Node.js handle child threads?</b>
</summary>

Node.js, in its essence, is a single thread process. It does not expose child threads and thread management methods to the developer. Technically, Node.js does spawn child threads for certain tasks such as asynchronous I/O, but these run behind the scenes and do not execute any application JavaScript code, nor block the main event loop.

If threading support is desired in a Node.js application, there are tools available to enable it, such as the ChildProcess module.

</details>

<details>
<summary>
46.  <b> What is the preferred method of resolving unhandled exceptions in Node.js? </b>
</summary>

Unhandled exceptions in Node.js can be caught at the `Process` level by attaching a handler for `uncaughtException` event.

```jsx harmony
process.on("uncaughtException", function (err) {
  console.log("Caught exception: " + err);
});
```

However, `uncaughtException` is a very crude mechanism for exception handling and may be removed from Node.js in the future. An exception that has bubbled all the way up to the `Process` level means that your application, and Node.js may be in an undefined state, and the only sensible approach would be to restart everything.

The preferred way is to add another layer between your application and the Node.js process which is called the domain.

Domains provide a way to handle multiple different I/O operations as a single group. So, by having your application, or part of it, running in a separate domain, you can safely handle exceptions at the domain level, before they reach the `Process` level.

</details>

<details>
<summary>
47.  <b> What is stream and what are types of streams available in Node.js?  </b>
</summary>

**Streams** are a collection of data that might not be available all at once and don’t have to fit in memory. Streams provide chunks of data in a continuous manner. It is useful to read a large set of data and process it.

There is four fundamental type of streams:

- Readable.
- Writeable.
- Duplex.
- Transform.

Readable streams as the name suggest used in reading a large chunk of data from a source. Writable streams are used in writing a large chunk of data to the destination.
Duplex streams are both readable and writable ( Eg socket). Transform stream is the duplex stream which is used in modifying the data (eg zip creation).

</details>

<details>
<summary>
48.  <b> What are the global objects of Node.js? </b>
</summary>

These objects are available in all modules:

- process - The process object is a global that provides information about, and control over, the current Node.js process.
- console - Used to print to stdout and stderr.
- buffer - Used to handle binary data.
</details>

<details>
<summary>
49.  <b> What is Piping in Node?  </b>
</summary>

**Piping** is a mechanism to connect output of one stream to another stream. It is normally used to get data from one stream and to pass output of that stream to another stream. There is no limit on piping operations.

</details>

<details>
<summary>
50.  <b> Name some of the events fired by streams </b>
</summary>

Each type of Stream is an EventEmitter instance and throws several events at different instance of times. For example, some of the commonly used events are:

- **data** - This event is fired when there is data is available to read.
- **end** - This event is fired when there is no more data to read.
- **error** - This event is fired when there is any error receiving or writing data.
- **finish** - This event is fired when all data has been flushed to underlying system
</details>

<details>
<summary>
51.  <b> What is the purpose of __filename variable? </b>
</summary>

The `__filename` represents the filename of the code being executed. This is the resolved absolute path of this code file. For a main program this is not necessarily the same filename used in the command line. The value inside a module is the path to that module file.

</details>

<details>
<summary>
52.  <b> What tools can be used to assure consistent code style? </b>
</summary>

- JSLint by Douglas Crockford
- JSHint
- ESLint
- JSCS

These tools are really helpful when developing code in teams, to enforce a given style guide and to catch common errors using static analysis.

</details>

<details>
<summary>
53.  <b> What's a stub? Name a use case </b>
</summary>

`Stubs` are functions/programs that simulate the behaviours of components/modules. Stubs provide canned answers to function calls made during test cases. Also, you can assert on with what these stubs were called.

A use-case can be a file read, when you do not want to read an actual file:

```jsx harmony
var fs = require("fs");

var readFileStub = sinon.stub(fs, "readFile", function (path, cb) {
  return cb(null, "filecontent");
});

expect(readFileStub).to.be.called;
readFileStub.restore();
```

</details>

<details>
<summary>
54.  <b>Does Node.js support multi-core platforms? And is it capable of utilizing all the cores? </b>
</summary>

Yes, Node.js would run on a multi-core system without any issue. But it is by default a single-threaded application, so it can’t completely utilize the multi-core system.

However, Node.js can facilitate deployment on multi-core systems where it does use the additional hardware. It packages with a Cluster module which is capable of starting multiple Node.js worker processes that will share the same port.

</details>

<details>
<summary>
55.  <b> Is Node.js entirely based on a single-thread? </b>
</summary>

Yes, it’s true that Node.js processes all requests on a single thread. But it’s just a part of the theory behind Node.js design. In fact, more than the single thread mechanism, it makes use of events and callbacks to handle a large no. of requests asynchronously.

Moreover, Node.js has an optimized design which utilizes both JavaScript and C++ to guarantee maximum performance. JavaScript executes at the server-side by Google Chrome v8 engine. And the C++ lib UV library takes care of the non-sequential I/O via background workers.

To explain it practically, let’s assume there are 100s of requests lined up in Node.js queue. As per design, the main thread of Node.js event loop will receive all of them and forwards to background workers for execution. Once the workers finish processing requests, the registered callbacks get notified on event loop thread to pass the result back to the user.

</details>

<details>
<summary>
56.  <b> Is Node.js entirely based on a single-thread?</b>
</summary>

Yes, it’s true that Node.js processes all requests on a single thread. But it’s just a part of the theory behind Node.js design. In fact, more than the single thread mechanism, it makes use of events and callbacks to handle a large no. of requests asynchronously.

Moreover, Node.js has an optimized design which utilizes both JavaScript and C++ to guarantee maximum performance. JavaScript executes at the server-side by Google Chrome v8 engine. And the C++ lib UV library takes care of the non-sequential I/O via background workers.

To explain it practically, let’s assume there are 100s of requests lined up in Node.js queue. As per design, the main thread of Node.js event loop will receive all of them and forwards to background workers for execution. Once the workers finish processing requests, the registered callbacks get notified on event loop thread to pass the result back to the user.

</details>

<details>
<summary>
57.  <b>When to not use Node.js? </b>
</summary>

We can use Node.js for a variety of applications. But it is a single threaded framework, so we should not use it for cases where the application requires long processing time. If the server is doing some calculation, it won’t be able to process any other requests. Hence, Node.js is best when processing needs less dedicated CPU time.

</details>

<details>
<summary>
58.  <b> Why to use Buffers instead of binary strings to handle binary data ?</b>
</summary>

Pure JavaScript does not able to handle straight binary data very well. Since Node.js servers have to deal with TCP streams for reading and writing of data, binary strings will become problematic to work with as it is very slow and has a tendency to break. That's why it is always advisable to use Buffers instead of binary strings to handle binary data.

</details>

<details>
<summary>
59.  <b> How to gracefully Shutdown Node.js Server? </b>
</summary>

We can gracefully shutdown Node.js server by using the generic signal called SIGTERM or SIGINT which is used for program termination. We need to call SIGTERM or SIGINT which will terminate the program and clean up the resources utilized by the program.

</details>

<details>
<summary>
60.  <b>What are the timing features of Node.js? </b>
</summary>

The Timers module in Node.js contains functions that execute code after a set period of time.

- setTimeout/clearTimeout - can be used to schedule code execution after a designated amount of milliseconds
- setInterval/clearInterval - can be used to execute a block of code multiple times
- setImmediate/clearImmediate - will execute code at the end of the current event loop cycle
- process.nextTick - used to schedule a callback function to be invoked in the next iteration of the Event Loop

```jsx harmony
function cb() {
  console.log("Processed in next iteration");
}
process.nextTick(cb);
console.log("Processed in the first iteration");
```

Output:

```jsx harmony
Processed in the first iteration
Processed in next iteration
```

</details>

<details>
<summary>
61.  <b>Explain usage of NODE_ENV </b>
</summary>

Node encourages the convention of using a variable called NODE_ENV to flag whether we’re in production right now. This determination allows components to provide better diagnostics during development, for example by disabling caching or emitting verbose log statements. Setting NODE_ENV to production makes your application 3 times faster.

```jsx harmony
// Setting environment variables in bash before starting the node process
$ NODE_ENV=development
$ node

// Reading the environment variable using code
if (process.env.NODE_ENV === “production”)
    useCaching = true;
```

</details>

<details>
<summary>
62.  <b>What is LTS releases of Node.js why should you care? </b>
</summary>

An LTS(Long Term Support) version of Node.js receives all the critical bug fixes, security updates and performance improvements.

LTS versions of Node.js are supported for at least 18 months and are indicated by even version numbers (e.g. 4, 6, 8). They're best for production since the LTS release line is focussed on stability and security, whereas the Current release line has a shorter lifespan and more frequent updates to the code. Changes to LTS versions are limited to bug fixes for stability, security updates, possible npm updates, documentation updates and certain performance improvements that can be demonstrated to not break existing applications.

</details>

<details>
<summary>
63.  <b>Provide some example of config file separation for dev and prod environments </b>
</summary>

A perfect and flawless configuration setup should ensure:

- keys can be read from file AND from environment variable
- secrets are kept outside committed code
- config is hierarchical for easier findability
- Consider the following config file:

```jsx harmony
var config = {
  production: {
    mongo: {
      billing: "****",
    },
  },
  default: {
    mongo: {
      billing: "****",
    },
  },
};

exports.get = function get(env) {
  return config[env] || config.default;
};
```

And it's usage:

```jsx harmony
const config = require("./config/config.js").get(process.env.NODE_ENV);
const dbconn = mongoose.createConnection(config.mongo.billing);
```

</details>

<details>
<summary>
64.  <b> How would you handle errors for async code in Node.js? </b>
</summary>

Handling async errors in callback style (error-first approach) is probably the fastest way to hell (a.k.a the pyramid of doom). It's better to use a reputable promise library or async-await instead which enables a much more compact and familiar code syntax like try-catch.

Consider promises to catch errors:

```jsx harmony
doWork()
  .then(doWork)
  .then(doOtherWork)
  .then((result) => doWork)
  .catch((error) => {
    throw error;
  })
  .then(verify);
```

or using async/await:

```jsx harmony
async function check(req, res) {
  try {
    const a = await someOtherFunction();
    const b = await somethingElseFunction();
    res.send("result");
  } catch (error) {
    res.send(error.stack);
  }
}
```

</details>

<details>
<summary>
65.  <b>  What's the difference between dependencies, devDependencies and peerDependencies in npm package.json file? </b>
</summary>

1. **dependencies** - Dependencies that your project needs to run, like a library that provides functions that you call from your code. They are installed transitively (if A depends on B depends on C, npm install on A will install B and C).

2. **devDependencies** - Dependencies you only need during development or releasing, like compilers that take your code and compile it into javascript, test frameworks or documentation generators. They are not installed transitively (if A depends on B dev-depends on C, npm install on A will install B only).

3. **peerDependencies** - Dependencies that your project hooks into, or modifies, in the parent project, usually a plugin for some other library or tool. It is just intended to be a check, making sure that the parent project (project that will depend on your project) has a dependency on the project you hook into. So if you make a plugin C that adds functionality to library B, then someone making a project A will need to have a dependency on B if they have a dependency on C. They are not installed (unless npm < 3), they are only checked for.
</details>

<details>
<summary>
66.  <b> How do you convert an existing callback API to promises?  </b>
</summary>

How to convert this callback code to Promise? Provide some examples.

```jsx harmony
function divisionAPI(number, divider, successCallback, errorCallback) {
  if (divider == 0) {
    return errorCallback(new Error("Division by zero"));
  }
  successCallback(number / divider);
}
```

Answer:

```jsx harmony
function divisionAPI(number, divider) {
  return new Promise(function (fulfilled, rejected) {
    if (divider == 0) {
      return rejected(new Error("Division by zero"));
    }
    fulfilled(number / divider);
  });
}

// Promise can be used with together async\await in ES7 to make the program flow wait for a fullfiled result
async function foo() {
  var result = await divisionAPI(1, 2); // awaits for a fulfilled result!
  console.log(result);
}

// Another usage with the same code by using .then() method
divisionAPI(1, 2).then(function (result) {
  console.log(result);
});
```

Node.js 8.0.0 includes a new util.promisify() API that allows standard Node.js callback style APIs to be wrapped in a function that returns a Promise.

```jsx harmony
const fs = require("fs");
const util = require("util");

const readfile = util.promisify(fs.readFile);

readfile("/some/file")
  .then((data) => {
    /** ... **/
  })
  .catch((err) => {
    /** ... **/
  });
```

</details>

<details>
<summary>
67.  <b> What are async functions in Node? Provide some examples</b>
</summary>

With the release of Node.js 8, the long awaited async functions have landed in Node.js as well. ES 2017 introduced Asynchronous functions. Async functions are essentially a cleaner way to work with asynchronous code in JavaScript.

**Async/Await is:**

- The newest way to write asynchronous code in JavaScript.
- It is non blocking (just like promises and callbacks).
- Async/Await was created to simplify the process of working with and writing chained promises.
- Async functions return a Promise. If the function throws an error, the Promise will be rejected. If the function returns a value, the Promise will be resolved.
- Async functions can make use of the await expression. This will pause the async function and wait for the Promise to resolve prior to moving on.

</details>

<details>
<summary>
68.  <b> Explain what is Reactor Pattern in Node.js? </b>
</summary>

Reactor Pattern is an idea of non-blocking I/O operations in Node.js. This pattern provides a handler(in case of Node.js, a callback function) that is associated with each I/O operation. When an I/O request is generated, it is submitted to a `demultiplexer`.

This demultiplexer is a notification interface that is used to handle concurrency in non-blocking I/O mode and collects every request in form of an event and queues each event in a queue. Thus, the demultiplexer provides the Event Queue.

At the same time, there is an Event Loop which iterates over the items in the Event Queue. Every event has a callback function associated with it, and that callback function is invoked when the Event Loop iterates.

</details>

<details>
<summary>
69.  <b> How would you scale Node application? </b>
</summary>

We can scale Node application in following ways:

- cloning using Cluster module.
- decomposing the application into smaller services – i.e micro services.
</details>

<details>
<summary>
70.  <b>Explain some Error Handling approaches in Node.js you know about. Which one will you use? </b>
</summary>

Error handling in an asynchronous language works in a unique way and presents many challenges, some unexpected.
There are four main error handling patterns in node:

1. **Error return value**- doesn't work asynchronously

```jsx harmony
var validateObject = function (obj) {
  if (typeof obj !== "object") {
    return new Error("Invalid object");
  }
};
```

2. **Error throwing** - well-establish pattern, in which a function does its thing and if an error situation arises, it simply bails out throwing an error. Can leave you in an unstable state. It requires extra work to catch them. Also wrapping the async calls in try/catch won't help because the errors happen asynchronously. To fix this, we need domains. Domains provide an asynchronous try...catch.

```jsx harmony
var validateObject = function (obj) {
  if (typeof obj !== "object") {
    throw new Error("Invalid object");
  }
};

try {
  validateObject("123");
} catch (err) {
  console.log("Thrown: " + err.message);
}
```

3. **Error callback** - returning an error via a callback is the most common error handling pattern in Node.js. Handling error callbacks can become a mess (callback hell or the pyramid of doom).

```jsx harmony
var validateObject = function (obj, callback) {
  if (typeof obj !== "object") {
    return callback(new Error("Invalid object"));
  }
  return callback();
};

validateObject("123", function (err) {
  console.log("Callback: " + err.message);
});
```

4. **Error emitting** - when emitting errors, the errors are broadcast to any interested subscribers and handled within the same process tick, in the order subscribed.

```jsx harmony
var Events = require("events");
var emitter = new Events.EventEmitter();

var validateObject = function (a) {
  if (typeof a !== "object") {
    emitter.emit("error", new Error("Invalid object"));
  }
};

emitter.on("error", function (err) {
  console.log("Emitted: " + err.message);
});

validateObject("123");
```

5. **Promises** for async error handling

```jsx harmony
doWork()
  .then(doWork)
  .then(doError)
  .then(doWork)
  .catch(errorHandler)
  .then(verify);
```

6. **Try...catch with async/await** - ES7 Async/await allows us as developers to write asynchronous JS code that look synchronous.

```jsx harmony
async function f() {
  try {
    let response = await fetch("http://no-such-url");
  } catch (err) {
    alert(err); // TypeError: failed to fetch
  }
}

f();
```

7. Await-to-js lib - async/await without try-catch blocks in Javascript

```jsx harmony
import to from 'await-to-js';

async function main(callback) {
    const [err,quote] = await to(getQuote());

    if(err || !quote) return callback(new Error('No Quote found');

    callback(null,quote);

}
```

</details>

<details>
<summary>
71.  <b> What is the difference between process.nextTick() and setImmediate() ? </b>
</summary>

The difference between process.nextTick() and setImmediate() is that process.nextTick() defers the execution of an action till the next pass around the event loop or it simply calls the callback function once the ongoing execution of the event loop is finished whereas setImmediate() executes a callback on the next cycle of the event loop and it gives back to the event loop for executing any I/O operations.

</details>

<details>
<summary>
72.  <b>  Why should you separate Express 'app' and 'server'?</b>
</summary>

Keeping the API declaration separated from the network related configuration (port, protocol, etc) allows testing the API in-process, without performing network calls, with all the benefits that it brings to the table: fast testing execution and getting coverage metrics of the code. It also allows deploying the same API under flexible and different network conditions. Bonus: better separation of concerns and cleaner code.

API declaration, should reside in app.js:

```jsx harmony
var app = express();
app.use(bodyParser.json());
app.use("/api/events", events.API);
app.use("/api/forms", forms);
```

Server network declaration, should reside in /bin/www:

```jsx harmony
var app = require("../app");
var http = require("http");

/**
 * Get port from environment and store in Express.
 */

var port = normalizePort(process.env.PORT || "3000");
app.set("port", port);

/**
 * Create HTTP server.
 */

var server = http.createServer(app);
```

</details>

<details>
<summary>
73.  <b> Rewrite the code sample without try/catch block </b>
</summary>

Consider the code:

```jsx harmony
async function check(req, res) {
  try {
    const a = await someOtherFunction();
    const b = await somethingElseFunction();
    res.send("result");
  } catch (error) {
    res.send(error.stack);
  }
}
```

Rewrite the code sample without try/catch block.

Answer:

```jsx harmony
async function getData() {
  const a = await someFunction().catch((error) => console.log(error));
  const b = await someOtherFunction().catch((error) => console.log(error));
  if (a && b) console.log("some result");
}
```

or if you wish to know which specific function caused error:

```jsx harmony
async function loginController() {
  try {
    const a = await loginService().catch((error) => {
      throw new CustomErrorHandler({
        code: 101,
        message: "a failed",
        error: error,
      });
    });
    const b = await someUtil().catch((error) => {
      throw new CustomErrorHandler({
        code: 102,
        message: "b failed",
        error: error,
      });
    });
    //someoeeoe
    if (a && b) console.log("no one failed");
  } catch (error) {
    if (!(error instanceof CustomErrorHandler)) {
      console.log("gen error", error);
    }
  }
}
```

</details>

<details>
<summary>
74.  <b> How the V8 engine works?  </b>
</summary>

V8 is a JavaScript engine built at the google development center, in Germany. It is open source and written in C++. It is used for both client side (Google Chrome) and server side (node.js) JavaScript applications.

V8 was first designed to increase the performance of the JavaScript execution inside web browsers. In order to obtain speed, V8 translates JavaScript code into more efficient machine code instead of using an interpreter. It compiles JavaScript code into machine code at execution by implementing a JIT (Just-In-Time) compiler like a lot of modern JavaScript engines such as SpiderMonkey or Rhino (Mozilla) are doing. The main difference with V8 is that it doesn’t produce bytecode or any intermediate code.

</details>

<details>
<summary>
75.  <b> How does the cluster module work? What’s the difference between it and a load balancer? </b>
</summary>

The cluster module performs fork from your server (at that moment it is already an OS process), thus creating several slave processes. The cluster module supports two methods of distributing incoming connections.

The first one (and the default one on all platforms except Windows), is the round-robin approach, where the master process listens on a port, accepts new connections and distributes them across the workers in a round-robin fashion, with some built-in smarts to avoid overloading a worker process.

The second approach is where the master process creates the listen socket and sends it to interested workers. The workers then accept incoming connections directly.

The difference between a cluster module and a load balancer is that instead of distributing load between processes, the balancer distributes requests.

</details>
