# Introduction to Express.js

Express.js is a minimal and flexible Node.js web application framework that provides a robust set of features for web and mobile applications. It is designed to make the process of building web applications and APIs with Node.js simpler and more manageable.

## Routing

Routing refers to determining how an application responds to a client request to a particular endpoint, which is a URI (or path) and a specific HTTP request method (GET, POST, PUT, DELETE, etc.). Here's a basic example of defining routes in Express:

```javascript
const express = require('express');
const app = express();

// Define a route handler for the default home page
app.get('/', (req, res) => {
  res.send('Hello World!');
});

// Define a route handler for a custom path
app.get('/about', (req, res) => {
  res.send('About Page');
});

// Start the server
app.listen(3000, () => {
  console.log('Server is running on http://localhost:3000');
});
```

## Middleware

* Middleware functions are functions that have access to the `request object (req)`, the `response object (res)`, and the next middleware function in the application's request-response cycle. They can perform tasks like logging, authentication, parsing request bodies, etc.

```javascript
// Middleware function to log requests
app.use((req, res, next) => {
  console.log(`${req.method} ${req.url}`);
  next();
});

// Middleware function to parse JSON bodies
app.use(express.json());

// Middleware function to handle errors
app.use((err, req, res, next) => {
  console.error(err.stack);
  res.status(500).send('Something broke!');
});
```

## Building RESTful APIs with Express

* Express makes it easy to build RESTful APIs by defining routes that correspond to the CRUD (Create, Read, Update, Delete) operations.

```javascript
// Define a route to get all items
app.get('/api/items', (req, res) => {
  res.json(items);
});

// Define a route to get a single item
app.get('/api/items/:id', (req, res) => {
  const item = items.find((item) => item.id === parseInt(req.params.id));
  if (!item) return res.status(404).send('Item not found');
  res.json(item);
});

// Define a route to create a new item
app.post('/api/items', (req, res) => {
  const item = {
    id: items.length + 1,
    name: req.body.name,
  };
  items.push(item);
  res.status(201).json(item);
});
```