# Node.js Notes

##### Nodejs Notes and General Javascript Code Snippets


#### For & While
```javascript
// For & while loops
var i = 0;
var countLimit = 8;

while (i < countLimit) {
    console.log('while ' + i);
    i++; // i = i + 1
};

for ( i = 0; i < countLimit; i++) {
  console.log('for: ' + i);
};
```
#### Variable Scope

```Javascript
var age = 24;

function localfunction () {
  var age = 0 // if defined locally, javascript will not reference global variable
  age = 0;
  // Variables within function not accessible outside that function...
}

localFunction();

console.log(age) // => 24

```

#### Closures

A function that has access to parent function variables.

```Javascript
function greetMaker (name) {
  function greet () {
    console.log('hello ' + name);
  }
  return greet;
}

var greetAndrew = greetMaker('Andrew');

greetAndrew(); // => 'hello Andrew'

var greetWorld = greetMaker('world');

greetWorld(); // => 'hello world'

// Example provided does not fully explain closures.

```
```Javascript
// Simple closure example, adds values to a base number:

function createAdder(basenumber) {
  return function(numberToAdd){
    return basenumber + numberToAdd
  }
}

var addTen = createAdder(10);

console.log(addTen(5)); // => 15

```

#### Node Scripts
 When running a node script, a node checks the package.json file for a keyname. if a keyname matches, 
 the associated console command is run. See "Scripts:" below for examples.

```Javascript
{
  "name": "password-manager",
  "version": "1.0.0",
  "description": "Manage your passwords locally",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",// From console: npm test
    "start": "node app.js" /// From console: npm start
  },
  "keywords": [
    "Erik",
    "Grueter"
  ],
  "author": "Erik Grueter",
  "license": "ISC",
  "dependencies": {
    "node-persist": "0.0.8"
  }
}
```

#### Require Node Packages
    To access an installed node package, use the built in require(); function in your app.js file
 

```Javascript
// App.js
console.log('starting password manager');
//Require Built in Node function.
var store = require("node-persist");
```



