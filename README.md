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
