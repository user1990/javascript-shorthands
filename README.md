Javascript Shorthand Coding Techniques
=====

> Techniques, shorthands, tips and tricks for faster and better readable JS development

## Add, distract, multiply, divide
```javascript
// Longhand
i = i + 5;
j = j - 3;
k = k * 10;
l = l / 2;

// Shorthand
i += 5;
j -= 3;
k *= 10;
l /= 2;
```

## Logical AND
```javascript
// Longhand
if (a > 10) {
   doSomething();
}

// Shorthand
a > 10 && doSomething();
```

## Logical OR
```javascript
// Longhand
if (a !== null || a !== undefined || a !== '') {
     let b = a
}

// Shorthand
let b = a  || 'new'
```

## Determine character position
```javascript
// Longhand
"myString".charAt(4)

// Shorthand
"myString"[4]
```

## if evaluation
```javascript
// Longhand
if (isTrue === true) {
  processTrue();
}

if (isTrue !== true) {
  processFalse();
}

// Shorthand 1
if (isTrue) {
  processTrue();
}

if (!isTrue) {
  processFalse();
}

// Shorthand 2
isTrue && processTrue();
isTrue || processFalse();
```

## for loop
```javascript
// Longhand
for (let i = 0; i < myArray.length; i++)

// Shorthand
for (let i of myArray)
```

## Array lookup
```javascript
// Longhand
if (array.indexOf(item) >= -1) {
  doSomething();
}

// Shorthand
if (~array.indexOf(item)) {
  doSomething();
}
```
The ~ operator will return a truthy value for anything but -1.

## Double bitwise NOT
```javascript
// Longhand
Math.floor(1.8) === 1  //true

// Shorthand
~~1.8 === 1  //true
```

## Coercing a string into a number
```javascript
// Longhand
const a = parseFloat("1234.56");
const b = parseInt("1234", 10);

// Shorthand
const c = +"1234"; // Number: 1234
const d = -"1234"; // Number: -1234
```

## Coercing a number into a string
```javascript
// Longhand
const a = 123.45;
const b = a.toString(10);

// Shorthand
const c = 1234 + '';
a += '';
```

## Coercing a value into a boolean
```javascript
// Longhand
const a = Boolean(expression);

// Shorthand
const a = !!expression;
```

## Call functions
```javascript
// Longhand
if (z == 3) {
  x();
} else {
  y();
}

// Shorthand
(z == 3 ? x : y)();
```

## Quick Powers
```javascript
// Longhand
Math.pow(2, 3) // 8

// Shorthand
2 ** 3; // 8
```

## Remove Final Digits
```javascript
// Longhand
let str = "1553"; 
Number(str.substring(0, str.length - 1)); // 155

// Shorthand
1553 / 10   | 0  // 155
1553 / 100  | 0  // 15
1553 / 1000 | 0  // 1
```

## Short-Circuiting
```javascript
// Longhand
if (person) {
  fetchProfile(person);
}

// Shorthand
person && fetchProfile(person);
```

## Destructuring axios request
```javascript
// Longhand
const result = axios.get(`https://ironhack-pokeapi.herokuapp.com/pokemon/${entry.id}`)
const data = result.data

// Shorthand
const { data } = await axios.get(...)
```

## Filter Unique Values
```javascript
const array = [1, 1, 2, 3, 5, 5, 1]
const uniqueArray = [...new Set(array)]; [1, 2, 3, 5] 
```

## Get the Last Item(s) in an Array
```javascript
let array = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9];
console.log(array.slice(-2)); // [8, 9]
```

## Format JSON Code
```javascript
const obj = { 
  foo: { bar: [11, 22, 33, 44], baz: { bing: true, boom: 'Hello' } } 
};

JSON.stringify(obj, null, 4); // The third parameter is the number of spaces used to beautify the JSON output. 
// =>"{
// =>    "foo": {
// =>        "bar": [
// =>            11,
// =>            22,
// =>            33,
// =>            44
// =>        ],
// =>        "baz": {
// =>            "bing": true,
// =>            "boom": "Hello"
// =>        }
// =>    }
// =>}"
```

## Swap variables with Array Destructuring
```javascript
let a = 'world', b = 'hello'
[a, b] = [b, a]
console.log(a) // hello
console.log(b) // world
```

## Async/Await with Destructuring
```javascript
const [user, account] = await Promise.all([
  fetch('/user'),
  fetch('/account')
])
```

## Find max value from array
```javascript
const arr = [123, 321, 32];
Math.max(...arr) // 321
```

## Logical operators
```javascript
true && true // true
false && true // false
true && false // false
false && false // false
true || true // true
true || false // true
false || true // true
false || false // false
```

- && : The first falsy value gets returned, if there is none, the last truthy value is being returned.
- ||: The first truthy value gets returned, if there is none, the operation will equal to the last falsy value.

```javascript
0 && {a: 1} // 0
false && 'a' // false
'2' && 5 // 5
[] || false // []
NaN || null // null
true || 'a' // true
```

## Optional chaining
```javascript
// Longhand
let data
if(myObj && myObj.firstProp && myObj.firstProp.secondProp && myObj.firstProp.secondProp.actualData) {
  data = myObj.firstProp.secondProp.actualData
}

// Shorthand
const data = myObj?.firstProp?.secondProp?.actualData
```

## Removing duplicate items from an array
```javascript
const removeDuplicateItems = arr => [...new Set(arr)];
removeDuplicateItems([42, 'foo', 42, 'foo', true, true]); // [42, "foo", true]
```




