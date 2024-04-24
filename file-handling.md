# File Operations and Streams in Node.js

## Reading Files

Node.js provides the `fs` module for file system operations. To read a file asynchronously, you can use the `fs.readFile()` method. Here's an example:

```javascript
const fs = require('fs');

fs.readFile('example.txt', 'utf8', (err, data) => {
  if (err) {
    console.error(err);
    return;
  }
  console.log(data);
});
```
## Writing Files
* `fs.writeFile()` method. Example:

```javascript
const fs = require('fs');

fs.writeFile('example.txt', 'Hello, World!', (err) => {
  if (err) {
    console.error(err);
    return;
  }
  console.log('File written successfully');
});
```

## Working with Directories
* To create a directory, use the `fs.mkdir()` method. 
* To remove a directory, use the `fs.rmdir()` method. Example:

```javascript
    const fs = require('fs');

// Create a directory
fs.mkdir('example', (err) => {
  if (err) {
    console.error(err);
    return;
  }
  console.log('Directory created successfully');
});

// Remove a directory
fs.rmdir('example', (err) => {
  if (err) {
    console.error(err);
    return;
  }
  console.log('Directory removed successfully');
});
```

## Streams and Buffers

* Streams are used to read or write data continuously. 
* Node.js provides four types of streams:          
  - Readable
  - Writable    
  - Duplex 
  - Transform streams. 
* Buffers are temporary storage areas in memory used for handling binary data.

```javascript
const fs = require('fs');

const readStream = fs.createReadStream('example.txt', 'utf8');

readStream.on('data', (chunk) => {
  console.log(chunk);
});

readStream.on('end', () => {
  console.log('File read complete');
});

```