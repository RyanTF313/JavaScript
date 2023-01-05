# JavaScript
 JavaScript Overview

 What is JavaScript?

 Mozilla's definition:

 JavaScript is a scripting or programming language that allows you to implement complex features on web pages — every time a web page does more than just sit there and display static information for you to look at — displaying timely content updates, interactive maps, animated 2D/3D graphics, scrolling video jukeboxes, etc. — you can bet that JavaScript is probably involved. It is the third layer of the layer cake of standard web technologies, two of which (HTML and CSS) we have covered in much more detail in other parts of the Learning Area.

 My definition:

 If you look at every web page as a person it is composed of 3 parts: structure, style, and actions. HTML is the structure, CSS is the style, and JS is the actions. It is what allows a web page to perform some type of action to complete a task.

 *PS*: It is not the same as Java

## Basics

### Primitive types

JavaScript has 5 primitive [types](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures):
`Number`, `String`, `Boolean`, `null`, and `undefined`.

| Type      | Examples                        |
|:----------|:--------------------------------|
| Number    | `1`, `42`, `-3` `1.04`, `NaN`, `Infinity`|
| String    | `'a simple string'`, `"Hi, my name is Chris."`, or empty strings: `''`, `""`|
| Boolean   | `true`, `false`                 |
| null      | `null`                          |
| undefined | `undefined`                     |

Primitive types represent **immutable** values.  We'll contrast this with
reference types in a later lesson.

The types Number and String both have large sets of possible values.  Boolean
has only two values and null and undefined each have just one.

### Literals

Literals represent specific values in the source code.
Some examples are `1`, `'A string'`, `null`.

### Variables

#### Declaring a variable: What is let and const vs. var

Prior to ES6 JavaScript had one way of declaring variables: `var`. Now there
are much better ways to declare variables: `let` and `const`. The basic rule of
thumb should be to use `const` when you don't need to reassign that variable,
and `let` when you do. You will continue to see `var` in legacy code bases and
documentation online, but you shouldn't use in your own code.

Variables name storage for the value they contain.  Because JavaScript is a
dynamically typed language, you can assign a value of one type to a variable and
then later assign a value of a different type to that same variable.

In JavaScript, `null` represents the explicitly omitted value, whereas
`undefined` represents the default omitted value.  Variables that have been
declared but are uninitialized or unset have the value `undefined`.

### Operators

Operators come in three classes, unary, binary (the most common), and ternary
(there is only one). These operators act on 1, 2, and 3 operands, respectively.

```js
// unary:
!true
// binary:
4 + 5
// ternary
isVegetarian ? 'no meat for you' : 'eats meat'
```

Operator precedence determines the order in which operators are evaluated.
Operators with higher precedence are evaluated first.

Associativity determines the order in which operators of the same precedence are
processed.

The following table lists a subset of the JavaScript
from higher to lower precedence.

| Type                                                 | Associativity | Operators                      |
|:-----------------------------------------------------|:--------------|:-------------------------------|
| grouping                                             | n/a           | `()`                           |
| postfix increment                                    | n/a           | `++` `--`                      |
| negation, numeric conversion, prefix increment, type | right-to-left | `!` `-` `+` `++` `--` `typeof` |
| multiplication, division, modulo                     | left-to-right | `*` `/` `%`                    |
| addition, subtraction                                | left-to-right | `+` `-`                        |
| relation, instance                                   | left-to-right | `<` `<=` `>` `>=` `instanceof` |
| strict equality                                      | left-to-right | `===` `!==`                    |
| logical and                                          | left-to-right | `&&`                           |
| logical or                                           | left-to-right | &#124;&#124;                   |
| conditional                                          | right-to-left | `?:`                           |
| assignment                                           | right-to-left | `=` `+=` `-=` `*=` `/=` `%=`   |

### Expressions

An expression is a combination of literals, variables, operators, function
invocations and sub-expressions that are interpreted and produce a value.  Not
all such combinations produce *sensible* results.

The simplest expression is a variable or literal. More
complicated expressions are formed by combining simpler expressions using
operators.

An expression with all of the variables replaced with literals that are equal to
the values of the variables will produce the same result.

Assignment changes the value of a variable.

```js
let name
console.log(name)
name = 'Brian'
console.log(name)
name = 'Sarah'
console.log(name)
```

Remember: JavaScript variables are untyped.

```js
let name
name = 'Brian'
name = 29
console.log(name + 1)
```

Although it doesn't cause an error, avoid confusing code like the above.

##### Constants

Constants must be initialized, assigned a value, when created. Uninitialized
constants are a syntax error.

```js
const variableOne
// const variableOne
//      ^^^^^^^^^^^^^
// SyntaxError: Missing initializer in const declaration
```

```js
const pi = 3.14159265359 // rounded
console.log(pi)
const e = 2.71828182846 // rounded
console.log(e)
```

#### Numeric expressions

Simple calculations:

```js
5 + 3
7 - 2
11 % 5
```

Expressions with variables only change values with assignment.

```js
let height
height = 80
height - 10
console.log(height)
height = height - 10
console.log(height)
```

What will `height` be at the end of the lines above?

Now let's compare some common methods of counting.

```js
let i
i = 0
i
i = i + 1
i
i += 1
i
++i
i
i++
i
```

*Note*: `++i` and `i++` are not the same! `++i` will increment i by 1 and then
evaluate i, whereas `i++` will evaluate i and then increment.

#### String expressions

```js
const firstName = 'Brian'
const lastName = 'Berzellini'
const fullName = firstName + ' ' + lastName
console.log(fullName)
```


```js
let bornOn = '1982 - 9 - 29'
console.log(bornOn)
bornOn = 1982 - 9 - 29
console.log(bornOn)
```

What happens if you don't enter the date as a string?

```js
let height = 72
height === 60
height > 72
height = 76
height >= 72
height > 72 && height < 78
```

The logical operators 'short circuit', which means they stop evaluating operands
as soon as the expression is `false` for `&&`, or `true` for `||`.

##### Truthy and Falsy Values

What do you think of when you hear 'truthy' and 'falsy'?

All values in JS are inherently truthy with the exception of these 6 values:

- `false`
- `undefined`
- `null`
- `0` and `-0`
- `NaN`
- `''`, `""`, and ` `` `

*Note*:  The negation (`!`) of a truthy value is `false` and the negation of a falsy
value is `true`.

```js
const truthyValue = 'A non-empty string'
const falsyValue = 0
console.log(!truthyValue)
console.log(!falsyValue)
```

#### Demo: Type conversions

The unary `+` operator attempts to convert its operand to a Number.  If
unsuccessful the result is `NaN`.

If either operand of the binary `+` operator is a string the operator converts
the other operator to a string.  Some results of this conversion are more useful
than others.

Note the difference between `3 + 5 + ' times'` and `'times ' + 3 + 5`?

`!` is the logical NOT operator. It always returns a boolean whose value is the
opposite of its operand. If its single operand is truthy, it returns false;
otherwise, it returns true.

[*Javascript 'Wat' Gotchas (1:25)*](https://www.destroyallsoftware.com/talks/wat)

#### Printing to the Console

As developers, we often want to take a look at the
inner workings of processing and just get a read on what variables store which
values at a specific time while our code is running. To do this we type
`console.log("Whatever we want to print out to the console.")`.

It's an extremely effective tool that often gets pulled out before
production, but can help give you an idea of what should be returned, and
a good point of reference for debugging.

#### `if` Statements

```js
let name
if (name === 'Brian') {
  console.log('Hi, Brian!')
} else if (name === 'Jeff') {
  console.log('Hi, Jeff!')
} else if (name === 'Chris') {
  console.log('Hi, Chris!')
} else {
  console.log('Hi, stranger.')
}
```

Change the string value of the `name` variable and save your file. Take a look at the updated value.

##### Ternary Operator

Ternary operators are basically a shorthand way of writing `if else` statements.
An example of a ternary operator can be found below:


This example might look a little bit confusing, but it is relatively simple if
we break it down: First, the statement before the question mark is evaluated as
being either `true` or `false`. If the statement is `true`, then the statement
to the left of the colon is executed. If it is `false`, the statement to the
right of the colon is executed.

#### `while` Loops

A simple while loop that logs from 0 - 9

```js
let i = 0
while (i < 10) {
  console.log(i)
  i++
}
```

```js
let count = 1

while (count < 5) {
  console.log('Inside of the loop, count is ' + count)
  count++
}

console.log('Outside of the loop, count is ' + count)
```

What if we change the value of `count`? Let's change the script so that we make
`count = 5` and then we can run the script again to see what changed.

#### String Interpolation

Take a look at `bin/guessName.js`, you may have noticed that we used the
variable `answer` in order to display the result of the user's input. The
combination of a string and a variable is called string interpolation. The
syntax for it looks like this:

This method of string interpolation is done using Template Literals.
*Note*: Make sure you are using *backticks* instead of single or double quotes.

#### `for` Loops

```js
for (let i = 0; i < 10; i++) {
  console.log(i)
}
```

That for loop was *almost* equivalent to:

```js
let i = 0
while (i < 10) {
  console.log(i)
  i++
}
```

Nesting conditionals in loops:

```js
for (let i = 0; i < 10; i++) {
  if (i === 5) {
    console.log('five!')
  } else {
    console.log('nah')
  }
}
```
