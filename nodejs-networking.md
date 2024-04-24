# HTTP Server/Client in Node.js

Node.js provides built-in modules `http` and `https` to create HTTP and HTTPS servers, respectively. These modules simplify the process of creating web servers and handling HTTP requests and responses.

## HTTP Server

To create an HTTP server in Node.js, you can use the `http` module's `createServer` method, passing a callback function that handles incoming requests and sends responses. Here's a basic example:

```javascript
const http = require('http');

const server = http.createServer((req, res) => {
  res.writeHead(200, { 'Content-Type': 'text/plain' });
  res.end('Hello, World!\n');
});

server.listen(3000, 'localhost', () => {
  console.log('Server running at http://localhost:3000/');
});


# Creating a REST API in Node.js

A RESTful API (Representational State Transfer) is an architectural style for designing networked applications. It uses standard HTTP methods (GET, POST, PUT, DELETE) to perform CRUD (Create, Read, Update, Delete) operations on resources.

## Steps to Create a REST API in Node.js

1. **Initialize a Node.js Project**:
   - Create a new directory for your project and navigate into it.
   - Run `npm init -y` to initialize a new Node.js project with default settings.

2. **Install Express**:
   - Express is a popular Node.js framework for building web applications and APIs.
   - Run `npm install express` to install Express as a dependency in your project.

3. **Create an Express Server**:
   - Create a new JavaScript file (e.g., `server.js`) in your project directory.
   - Use the following code to create a basic Express server:

     ```javascript
     const express = require('express');
     const app = express();
     const PORT = 3000;

     // Define a route to handle GET requests
     app.get('/api', (req, res) => {
       res.json({ message: 'Hello, World!' });
     });

     // Start the server
     app.listen(PORT, () => {
       console.log(`Server running at http://localhost:${PORT}`);
     });
     ```

4. **Run the Server**:
   - Run `node server.js` in your terminal to start the Express server.
   - Open a web browser and navigate to `http://localhost:3000/api` to see the API response.

5. **Implement CRUD Operations**:
   - Use Express routes to implement CRUD operations for your API.
   - For example, you can create routes for handling POST, PUT, and DELETE requests to manage resources.

6. **Use Middleware** (Optional):
   - Express middleware functions can be used to perform additional processing on incoming requests.
   - For example, you can use middleware to parse request bodies, authenticate users, or handle errors.

7. **Deploy Your API** (Optional):
   - Once your API is ready, you can deploy it to a hosting service (e.g., Heroku, AWS, Azure) to make it accessible over the internet.

This is a basic example of creating a REST API in Node.js using Express. Depending on your project requirements, you may need to add more routes, middleware, and functionality to your API.


# Handling POST and GET Requests in Node.js

Node.js provides the `http` module to create a web server and handle HTTP requests. To handle POST and GET requests, you can use the `http` module's `createServer` method and parse the request data accordingly.

## Handling GET Requests

To handle GET requests, you need to extract the query parameters from the request URL. Here's a basic example:

```javascript
const http = require('http');
const url = require('url');

const server = http.createServer((req, res) => {
  const parsedUrl = url.parse(req.url, true);
  const queryParams = parsedUrl.query;
  res.writeHead(200, { 'Content-Type': 'text/plain' });
  res.end(`Received GET request with parameters: ${JSON.stringify(queryParams)}`);
});

server.listen(3000, () => {
  console.log('Server running at http://localhost:3000/');
});
