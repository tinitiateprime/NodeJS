# HTTP Module
*  http - The HTTP module can create an HTTP server that listens to server ports and gives a response back to the client.

```
    var http = require('http');

http.createServer(function (req, res) {
  res.write('Hello World!'); 
  res.end(); 
}).listen(8080); 

```

*  res.write - write  a response to the client
*  res.end - end the response
* The function passed into the http.createServer() method, will be executed when someone tries to access the computer on port 8080.

* Save the code above in a file called "server.js", and initiate the file:


```
   node server.js
```

# Node File System

``` 
 var fs = require('fs'); 
```

# Common use for the File System module:

- Read files
- Create files
- Update files
- Delete files
- Rename files

## Read Files

* the fs.readfiles() method is used to read the file system on your computer.

* Create a demo html file that returns contetnt....

### demofile1.html
```
 demofile1.html

<html>
<body>
<h1>My Header</h1>
<p>My paragraph.</p>
</body>
</html>
```

* Create a Node js file that reads HTML file and returns content
```
 server.js

var http = require('http');
var fs = require('fs');
http.createServer(function (req, res) {
  fs.readFile('demofile1.html', function(err, data) {
    res.writeHead(200, {'Content-Type': 'text/html'});
    res.write(data);
    return res.end();
  });
}).listen(8080);

```

* run the code in server.js

```
   node server.js
```

## Create Files

* The File System module has methods for creating new files:
 
- fs.appendFile()
- fs.open()
- fs.writeFile()

* The fs.appendFile() method appends specified content to a file. If the file does not exist, the file will be created:

```
var fs = require('fs');

fs.appendFile('mynewfile1.txt', 'Hello content!', function (err) {
  if (err) throw err;
  console.log('Saved!');
});

```

### fs.writeFile()
* The fs.writeFile() method replaces the specified file and content if it exists. If the file does not exist, a new file, containing the specified content, will be created:

```
var fs = require('fs');

fs.writeFile('mynewfile3.txt', 'Hello content!', function (err) {
  if (err) throw err;
  console.log('Saved!');
});

```
### Update Files

* The fs.appendFile() method appends the specified content at the end of the specified file:

