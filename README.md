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

## If evaluation
```javascript
// Longhand
if (isTrue) {
  processTrue();
}

if (!isTrue) {
  processFalse();
}

// Shorthand 
isTrue && processTrue();
isTrue || processFalse();
```

## For loop
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

## Decimal Base Exponents
```javascript
// Longhand
for (let i = 0; i < 10000; i++) {}

// Shorthand
for (let i = 0; i < 1e7; i++) {}

// All the below will evaluate to true
1e0 === 1;
1e1 === 10;
1e2 === 100;
1e3 === 1000;
1e4 === 10000;
1e5 === 100000;
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

## Filter Unique Values or remove duplicates from array
```javascript
const array = [1, 1, 2, 3, 5, 5, 1]
const uniqueArray = [...new Set(array)]; // [1, 2, 3, 5] 
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

## Merge Objects
```javascript
const person = { name: 'David', gender: 'Male' };
const tools = { computer: 'Mac', editor: 'Atom' };
const attributes = { handsomeness: 'Extreme', hair: 'Brown', eyes: 'Blue' };

const summary = {...person, ...tools, ...attributes};
/* 
Object {
  "computer": "Mac",
  "editor": "Atom",
  "eyes": "Blue",
  "gender": "Male",
  "hair": "Brown",
  "handsomeness": "Extreme",
  "name": "David",
}
*/
```

## Get Query String Parameters
```javascript
// Assuming "?post=1234&action=edit"
const urlParams = new URLSearchParams(window.location.search);

console.log(urlParams.has('post')); // true
console.log(urlParams.get('action')); // "edit"
console.log(urlParams.getAll('action')); // ["edit"]
console.log(urlParams.toString()); // "?post=1234&action=edit"
console.log(urlParams.append('active', '1')); // "?post=1234&action=edit&active=1"
```

## Convert array numbers to strings
```javascript
const strArr = [1,2,3,4,5].map(String); // ["1","2","3","4","5"]
```

## Array destructuring, rest
```javascript
const names = ['Jack', 'Janet', 'John', 'Jessie', 'Jaqueline', 'Jerry', 'Justin', 'Julie', 'Jake'];
const [first, second, third, ...theRest] = names;

console.log(first); // "Jack"
console.log(theRest); // ["Jessie", "Jaqueline", "Jerry", "Justin", "Julie", "Jake"]
```

## Skip values by leaving the slot with a comma when Destructuring 
```javascript
const [,, three] = [1, 2, 3, 4, 5, 6, 7];
console.log(`I selected ${three}.`); // "I selected 3."
```

## Some Reduce magic combination
```javascript
const ingredients = ['wine', 'tomato', 'onion', 'mushroom']
const cook = ingredient => {
  return `cooked ${ingredient}`
}
const wineReduction = ingredients.reduce((sauce, item, index, array) => {
  return (index < array.length - 1) ? sauce += `${cook(item)}, ` : sauce += `${cook(item)}`
}, '')

// wineReduction = "cooked wine, cooked tomato, cooked onion, cooked mushroom"
```

## Combine filter, map, reduce example
```javascript
// Objective: get the total score of force users only
const personnel = [
  {
    id: 5,
    name: "Luke Skywalker",
    pilotingScore: 98,
    shootingScore: 56,
    isForceUser: true,
  },
  {
    id: 82,
    name: "Sabine Wren",
    pilotingScore: 73,
    shootingScore: 99,
    isForceUser: false,
  },
  {
    id: 22,
    name: "Zeb Orellios",
    pilotingScore: 20,
    shootingScore: 59,
    isForceUser: false,
  },
  {
    id: 15,
    name: "Ezra Bridger",
    pilotingScore: 43,
    shootingScore: 67,
    isForceUser: true,
  },
  {
    id: 11,
    name: "Caleb Dume",
    pilotingScore: 71,
    shootingScore: 85,
    isForceUser: true,
  },
];

const totalJediScore = personnel
  .filter(person => person.isForceUser)
  .map(jedi => jedi.pilotingScore + jedi.shootingScore)
  .reduce((acc, score) => acc + score, 0);
```

## Object.entries/Object.fromEntries turn object to multidimensional array and back into an object
```javascript
const students = {
  amelia: 20,
  beatrice: 22,
  cece: 20,
  deirdre: 19,
  eloise: 21
}

const overTwentyOne = Object.entries(students).filter(([name, age]) => age >= 21); // [ [ 'beatrice', 22 ], [ 'eloise', 21 ] ]
const drinkingAgeStudents = Object.fromEntries(overTwentyOne); // { beatrice: 22, eloise: 21 }
```

## Array flat to flatten multi-dimensional arrays
```javascript
const courseStudents = [
  [ 'Janet', 'Martha', 'Bob', [ 'Phil', 'Candace' ] ],
  [ 'Wilson', 'Taylor' ],
  [ 'Edith', 'Jacob', 'Peter', 'Betty' ]
]

const flattenByTwoLevel = courseStudents.flat(2) //The depth level specifying how deep a nested array structure should be flattened. Defaults to 1.
console.log(flattenOneLevel)
// [
//   'Janet',
//   'Martha',
//   'Bob',
//   [ 'Phil', 'Candace' ],
//   'Wilson',
//   'Taylor',
//   'Edith',
//   'Jacob',
//   'Peter',
//   'Betty'
// ]

- For an unknown depth with the intention of fully flattening the array the argument of Infinity can be used.
const alwaysFlattened = courseStudents.flat(Infinity)
console.log(alwaysFlattened)
// [
//   'Janet',   'Martha',
//   'Bob',     'Phil',
//   'Candace', 'Wilson',
//   'Taylor',  'Edith',
//   'Jacob',   'Peter',
//   'Betty'
// ]
```


