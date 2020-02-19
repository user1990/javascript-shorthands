Javascript Shorthand Coding Techniques
=====

> Techniques, tips and tricks for fater JS development

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
