# Reference Types

Javascript has three different reference types:

- Plain Object
- Array
- Function

All JavaScript reference types are technically objects, which we will discuss more
in a later lesson but for now we will think of objects, arrays and functions individually.

`Object` and `Array` are used to hold collections.

`Function` holds encapsulated executable code.

All three can be created using reference type literals.  The following shows the
simplest examples of these types created with literal syntax:

```js
const list = []
const dictionary = {}
const code = function () {}
```
### Object examples

```js
// Create an empty object literal
const emptyDictionary = {}

// Create an object literal with values
const car = {
  make: 'Ford',
  model: 'Mustang',
  year: 1999
}

// Read value from an Object, use key
car['make']
car.make

// Update value in an Object, use key
car.make = 'Toyota'

// Add value to an Object, use key
car.topSpeed = 120
```
### Object iteration (accessing object data)

```js
const car = {
  make: 'Ford',
  model: 'Mustang',
  year: 1999
}

// Individually print message for each property of object
console.log(car.make)
console.log(car.model)
console.log(car['year'])

// Loop through object using key
for (const key in car){
  console.log(car[key])
}
```

### Array examples

```js
// Create an empty array literal
const list = []

// Create an array literal with values
const anotherList = ['Nelly', 100, false, 2]

// Read value from an Array, use index
anotherList[0]
anotherList[2]

// Update value in an Array, use index
anotherList[2] = true

// Add value to an Array, use index
anotherList[5] = 'Add Me'
```

### Function examples

In mathematics, a function maps one or more inputs to a single output.

JavaScript isn't that strict, allowing zero inputs or no specified output.

```js
const hello = function () {
  console.log('Hello')
}

hello()
```

Functions can accept inputs

```js
const hello = function (name) {
  console.log('Hello ' + name)
}

hello('Mike')
```

Does the result of `hello` change depending on the arguments
used?

What can we do with functions?

Functions provide important parts of the building blocks of programs,
abstraction and encapsulation.

It is important to remember that `console.log` prints its arguments to the
`console` (the terminal using node, the console area of the debug tools using
chrome) but does not return a value. *this is a common point of confusion*.
`console.log` does *not* return a value (it returns `undefined`).

```js
const addOne = function (num) {
  return num + 1
}

const addOneNoReturn = function (num) {
  num + 1
}

const sum = addOne(10) // ?

const sum = addOneNoReturn(10) // ?
```

The important piece to remember is that you need the `return` keyword to return
a value. If you forget it or choose not to include it, the function still
returns something to the caller, and it will be `undefined`.

Strictly speaking, all JavaScript functions evaluate to a value, but that value
is `undefined` if we do not provide a return (explicitly or implicitly).

```js
const helloWorld = function () {
  return 'Hello World!'
}

const hello = function (name) {
  return 'Hello ' + name
}
```

### Parameters and Arguments

When you create a function, you specify the parameters.  When you call a
function, you specify the arguments (which are the values that the parameters
are set to when your function executes).

In JavaScript, functions can be defined as taking zero or more arguments.

```js
const zero = function () {
  return 0
}

// You call this function by writing: `zero()`

const one = function (param) {
  return param
}

// You call this function by writing: `one('argumentExample')`

const three = function (param1, param2, param3) {
  return param2
}

// You call this function by writing: `three(1, 'two', 'example')`

// What would happen if we called this function using only one argument?

three(1)
```

What is the result of this code?

```js
const add = function (a, b) {
  return a + b
}

add(1, 2) // ?
add(2, 'cat') // ?
add('cat', 'dog') // ?
```