# Creating Your First Node.js Application

Node.js allows you to build server-side applications using JavaScript. In this guide, we'll walk through creating a simple "Hello, World!" application.

## Prerequisites

Before you begin, ensure you have Node.js installed on your machine. You can download it from the [Node.js website](https://nodejs.org/).

## Steps

1. **Create a New Project Directory**:
   - Open your terminal or command prompt.
   - Create a new directory for your project:
     ```sh
     mkdir my-node-app
     cd my-node-app
     ```

2. **Initialize Your Project**:
   - Initialize a new Node.js project by creating a `package.json` file:
     ```sh
     npm init -y
     ```

3. **Create Your Main JavaScript File**:
   - Create a new file named `index.js`:
     ```sh
     touch index.js
     ```

4. **Write Your Application Code**:
   - Open `index.js` in a text editor and add the following code:
     ```javascript
     const http = require('http');

     const hostname = '127.0.0.1';
     const port = 3000;

     const server = http.createServer((req, res) => {
       res.statusCode = 200;
       res.setHeader('Content-Type', 'text/plain');
       res.end('Hello, World!\n');
     });

     server.listen(port, hostname, () => {
       console.log(`Server running at http://${hostname}:${port}/`);
     });
     ```

5. **Run Your Application**:
   - Start your Node.js application by running:
     ```sh
     node index.js
     ```
   - Open a web browser and navigate to `http://localhost:3000/`. You should see "Hello, World!" displayed in the browser.

6. **Conclusion**:
   - Congratulations! You've created your first Node.js application. From here, you can continue to build more complex applications using Node.js and its vast ecosystem of packages and libraries.

