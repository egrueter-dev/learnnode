# Node Noted
Nodejs Notes and code snippets


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

