# Asynchronous Programming in Node.js

Asynchronous programming in Node.js allows you to perform operations without blocking the execution of other code. There are several ways to handle asynchronous operations:

## Callbacks

Callbacks are functions passed as arguments to other functions, to be executed later when the operation is completed. They are a common pattern in Node.js, but can lead to callback hell in complex scenarios.

Example of using callbacks:

```javascript
fs.readFile('file.txt', 'utf8', (err, data) => {
  if (err) {
    console.error(err);
    return;
  }
  console.log(data);
});
```

## Promises

Promises are objects representing the eventual completion or failure of an asynchronous operation. 

They provide a cleaner way to handle asynchronous code compared to callbacks, especially when dealing with multiple asynchronous operations.

```javascript
const readFile = (fileName) => {
  return new Promise((resolve, reject) => {
    fs.readFile(fileName, 'utf8', (err, data) => {
      if (err) {
        reject(err);
        return;
      }
      resolve(data);
    });
  });
};

readFile('file.txt')
  .then(data => console.log(data))
  .catch(err => console.error(err));
```

## Async/Await

Async functions in JavaScript allow you to write asynchronous code that looks synchronous. They use the `async` keyword before the function declaration and `await` keyword before asynchronous operations.

Async/await is built on top of promises and provides a more readable and maintainable way to write asynchronous code.

```javascript
const readFile = async (fileName) => {
  try {
    const data = await fs.promises.readFile(fileName, 'utf8');
    console.log(data);
  } catch (err) {
    console.error(err);
  }
};

readFile('file.txt');
```

