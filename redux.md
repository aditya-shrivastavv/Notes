# Redux

- [Redux](#redux)
  - [Installation ↑](#installation-)
  - [Three Core Concepts of Redux ↑](#three-core-concepts-of-redux-)
  - [Three Principles of Redux ↑](#three-principles-of-redux-)
    - [1. The State of your Whole Application is stored in an Object Tree within a Single Store ↑](#1-the-state-of-your-whole-application-is-stored-in-an-object-tree-within-a-single-store-)
    - [2. The only way to change the state is to emit an Action, an Object describing what happened ↑](#2-the-only-way-to-change-the-state-is-to-emit-an-action-an-object-describing-what-happened-)
    - [3. To specify how the state tree is transformed by actions, you write pure Reducers ↑](#3-to-specify-how-the-state-tree-is-transformed-by-actions-you-write-pure-reducers-)
  - [Redux Flow ↑](#redux-flow-)
    - [Action ↑](#action-)
    - [Reducer ↑](#reducer-)

**Redux** is a _predictable_ _state_ _container_ for JavaScript apps. It makes **state management** simple and scalable. It is a great tool for managing state in a React application. It doesn't only works with React it can be used with any other JavaScript framework or library.

What Redux does can also be done with React's context API. But Redux is a lot more powerful and has a lot more features. It is also a lot more complex to use. We can track the state of our application with **Redux DevTools**. It is a great tool for debugging and development.

It is sometimes hard to use redux directly in our react application that's why we use libraries like **react-redux**. It makes it easier to use redux in our react application.

## Installation [↑](#redux)

```bash
npm i redux            #plain redux
npm i react-redux      #redux for react
```

## Three Core Concepts of Redux [↑](#redux)

| Redux   | Purpose                            | Analogy (Cake Shop) |
| ------- | ---------------------------------- | ------------------- |
| Store   | Holds the state of our application | Cake Shop           |
| Action  | Describes what happened            | Ordering a Cake     |
| Reducer | Ties the action and store together | Shopkeeper          |

## Three Principles of Redux [↑](#redux)

### 1. The State of your Whole Application is stored in an Object Tree within a Single Store [↑](#redux)

Maintain our application state in a single object which would be managed by redux store.

```js
{
  numberofCakes: 10,
  numberofIceCreams: 20,
  paymentTaken: false
}
```

### 2. The only way to change the state is to emit an Action, an Object describing what happened [↑](#redux)

To update the state of your app, you need to let redux know about that with an action.
Not allowed to directly update the state of the store.

```js
{
  type: "BUY_CAKE",
}
```

First let the shopkeeper know that you want to buy a cake. Then the shopkeeper will update the state of the store.

### 3. To specify how the state tree is transformed by actions, you write pure Reducers [↑](#redux)

A reducer is a function that takes the current state and an action as arguments, and returns a new state result.

```js
Reducer = (previousState, action) => newState;
```

## Redux Flow [↑](#redux)

![Redux Flow](https://larsbergqvist.files.wordpress.com/2021/07/redux-flow.png)

---

### Action [↑](#redux)

```js
const BUY_CAKE = "BUY_CAKE";
{
  type: BUY_CAKE,
  info: "First Redux Action"
}
```

This is an action, that's it. **An action is just a plain JavaScript object that has a type property**. The type property describes the kind of action that is being performed. The type property is usually defined as a string constant. It's a good practice to define action types as string constants. Because string constants are easier to misspell than variables, and string constants are easier to reuse.

> Action Creators

Action creators are functions that returns an action.

```js
const buyCake = () => {
  return {
    type: BUY_CAKE,
    info: "First Redux Action",
  };
};
```

### Reducer [↑](#redux)

It is a function that accepts the state and action as arguments, and returns the new state.

```js
const initialState = {
  numberOfCakes: 10,
};

const reducer = (state = initialState, action) => {
  switch (action.type) {
    case BUY_CAKE:
      return {
        ...state,
        numberOfCakes: state.numberOfCakes - 1,
      };
    default:
      return state;
  }
};
```

we are not allowed to mutate the state directly. We have to return a new state object. We can use the spread operator to copy the properties of the previous state into a new object.
