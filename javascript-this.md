# The "this" Keyword in JavaScript

## JS in not Dynamically Scoped

```js
var teacher = "Kyle";

function ask(question) {
  console.log(teacher, question); // Kyle, Who?
}

function otherClass() {
  var teacher = "Suzy";

  ask("Who?");
}

otherClass();
```

As we know JS is a lexically scoped language not dynamically scoped. So here we should not expect the value of `teacher` to be `Suzy` inside the `ask` function.

## So make it behave as Dynamic through `this`

```js
var teacher = "Kyle";

function ask(question) {
  console.log(this.teacher, question); // Suzy, Who?
}

function otherClass() {
  var myContext = {
    teacher: "Suzy",
  };

  ask.call(myContext, "Who?");
}

otherClass();
```

Here we are using the `call` method on the `ask` function to make it behave as a dynamically scoped function. We are passing the context object as the first argument to the `call` method. The `this` keyword inside the `ask` function will be bound to the `myContext` object.

## Different ways to Invoke a Function

### 1. this: implicit binding

```js
var workshop = {
  teacher: "Kyle",
  ask(question) {
    console.log(this.teacher, question);
  },
};

workshop.ask("Who?"); // Kyle, Who?
```

Here we are invoking the `ask` function as a method on the `workshop` object. So the `this` keyword inside the `ask` function will be bound to the `workshop` object **implicitly**.

### 2. this: dynamic binding -> sharing behavior

```js
function ask(question) {
  console.log(this.teacher, question);
}

var workshop1 = {
  teacher: "Kyle",
  ask: ask,
};
var workshop2 = {
  teacher: "Suzy",
  ask: ask,
};

workshop1.ask("Who?"); // Kyle, Who?
workshop2.ask("Who?"); // Suzy, Who?
```

`this` gets a diffent context object each time the function is invoked.

### 3. this: explicit binding

```js
function ask(question) {
  console.log(this.teacher, question);
}

var workshop1 = {
  teacher: "Kyle",
};
var workshop2 = {
  teacher: "Suzy",
};

ask.call(workshop1, "Who?"); // Kyle, Who?
ask.call(workshop2, "Who?"); // Suzy, Who?
```

Here we are using the `call` method to explicitly bind the `this` keyword to the `workshop1` and `workshop2` objects.

### 4. this: hard binding

```js
var workshop = {
  teacher: "Kyle",
  ask(question) {
    console.log(this.teacher, question);
  },
};

setTimeout(workshop.ask, 10, "Why?");
// undefined Why?

setTimeout(workshop.ask.bind(workshop), 10, "Hard bound this!");
// Kyle Hard bound this!
```

The `setTimeout(workshop.ask, 10, "Why?")` will not work as expected because the `this` keyword inside the `ask` function will be bound to the `window` object. So we need to **explicitly** bind the `this` keyword to the `workshop` object using the `bind` method.

### 5. this: new binding

```js
function ask(question) {
  console.log(this.teacher, question);
}

var newEmptyObject = new ask("what is 'new' doing here?");
// undefined what is 'new' doing here?
```

The point of `new` keyword is to invoke a function with a this keyword pointing at a whole new empty object.

- how `new` works when invoked with a function
  1. create a brand new empty object
  2. \*links that object to another object
  3. call function with `this` set to the new object
  4. if function does not return an object assume return of `this`

### 6. this: default binding

```js
var teacher = "Kyle";

function ask(question) {
  console.log(this.teacher, question);
}

function ask2(question) {
  "use strict";
  console.log(this.teacher, question);
}

ask("How are you?"); // Kyle How are you?
ask2("How are you?"); // Error!!!
```
