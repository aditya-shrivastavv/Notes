# var, let & const

what's the difference between `var`, `let` and `const`?

- [var, let \& const](#var-let--const)
  - [`var` ↑](#var-)
    - [`var` the **PROBLEM** ↑](#var-the-problem-)
  - [`let` ↑](#let-)
  - [`const` ↑](#const-)

## `var` [↑](#var-let--const)

- `var` is **function** scoped

```js
var greet = "say hi";

function foo() {
  var hello = "hello";
}

console.log(hello); // ReferenceError: hello is not defined
```

- `var` can be redeclared and as well as updated

```js
// redeclared
var greet = "say hi";
var greet = "say Hello instead";
console.log(greet); // "say Hello instead"

// updated
var greet = "say hi";
greet = "say Hello instead";
console.log(greet); // "say Hello instead"
```

- `var` is **hoisted** to the top of the function scope, it moves the declaration to the top of the file
- means that you can use a variable before it's declared, but the value will be `undefined`

```js
console.log(greet); // undefined
var greet = "say hi";
```

### `var` the **PROBLEM** [↑](#var-let--const)

- var is not block scoped, its only **function** scoped

```js
var greet = "say hi";
if (true) {
  var greet = "say Hello instead";
}
console.log(greet); // "say Hello instead" // PROBLEM
```

## `let` [↑](#var-let--const)

- `let` is **block** scoped
- we all are used to use this type of scope in other languages

```js
let greet = "say hi";

function foo() {
  let greet = "hello";
  console.log(greet); // "hello"
}

console.log(greet); // "say hi"
```

- `let` can be updated but not redeclared

```js
let greet = "say hi";

// updated
greet = "say Hello instead";
console.log(greet); // "say Hello instead"

// redeclared
let greet = "say hi"; // SyntaxError: Identifier 'greet' has already been declared
```

## `const` [↑](#var-let--const)

- `const` is same as `let` but it can't be updated or redeclared

```js
const greet = "say hi";

// updated
greet = "say Hello instead"; // TypeError: Assignment to constant variable.
```

- it cannot be reassigned a new value but it can be mutated

```js
const person = {
  name: "John",
  age: 30,
};

person.name = "Peter";
person.age = 32;

console.log(person); // {name: "Peter", age: 32}
```
