# Javascript Functions

## Function Declaration

```js
function myFunction() {
  // code to be executed
}
```

## Function Expression

```js
var myFunction = function () {
  // code to be executed
};
```

| Function Declartion                                                                            | Function Expression                                                                               |
| ---------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| Function declarations are **hoisted**                                                          | Function expressions are not **hoisted**                                                          |
| The function in function declaration can be accessed before and after the function definition. | The function in function expression can be accessed only after the function definition.           |
| A function declaration must have a function name                                               | A function expression can have function with or without name                                      |
| These are executed before any other code and analyzed by the compiler.                         | Function expressions load and execute only when the program interpreter reaches the line of code. |

> you will get an error if you try to call a function expression before it is defined, but you can call a function declaration before it is defined due to hoisting.

## Which one to use?

- function experession are mostly used these days because they are not hoisted and they are not available before the line of code is executed that makes the code more readable and easy to understand.
- there is no universal answer to this question, it depends on the situation and the developer's preference.

## IIFE (Immediately Invoked Function Expression)

```js
(function () {
  // code to be executed
})();
```

- IIFE is a function that is executed immediately after it is created.
- these are used to create a new scope and to avoid polluting the global scope.

## Another Tricks

### the `arguments` keyword

```js
function myFunction(a, b, c) {
  // logs out all the arguments in order
  console.log(arguments);
}
```

### Rest Parameters

```js
function myFunction(...args) {
  // args can be any name
  // args is an object that contains all the arguments
  console.log(args.props1, args.props2);
}
```

## Arrow Functions

```js
const myFunction = () => {
  // code to be executed
};

const myFunction = (a, b) => a + b;
```

- Arrow functions can be named or anonymous.
- Arrow functions are always in expression form.

They take `this` from the surrounding scope and cannot make their own `this`.

## Higher Order Functions

- A function that takes another function as an argument or returns a function as a result is called a higher-order function.

```js
function myFunction(a, b, callback) {
  // code to be executed
  callback();
}
```
