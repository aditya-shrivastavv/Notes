# Redux

**Redux** is a _predictable_ _state_ _container_ for JavaScript apps. It makes **state management** simple and scalable. It is a great tool for managing state in a React application. It doesn't only works with React it can be used with any other JavaScript framework or library.

What Redux does can also be done with React's context API. But Redux is a lot more powerful and has a lot more features. It is also a lot more complex to use. We can track the state of our application with **Redux DevTools**. It is a great tool for debugging and development.

It is sometimes hard to use redux directly in our react application that's why we use libraries like **react-redux**. It makes it easier to use redux in our react application.

## Installation

```bash
npm i redux            #plain redux
npm i react-redux      #redux for react
```

## Three Core Concepts of Redux

| Redux   | Purpose                            | Analogy (Cake Shop) |
| ------- | ---------------------------------- | ------------------- |
| Store   | Holds the state of our application | Cake Shop           |
| Action  | Describes what happened            | Ordering a Cake     |
| Reducer | Ties the action and store together | Shopkeeper          |

## Three Principles of Redux

> **1**. The State of your Whole Application is stored in an Object Tree within a Single Store.

Maintain our application state in a single object which would be managed by redux store.

```js
{
  numberofCakes: 10,
  numberofIceCreams: 20,
  paymentTaken: false
}
```

> **2**. The only way to change the state is to emit an Action, an Object describing what happened.

To update the state of your app, you need to let redux know about that with an action.
Not allowed to directly update the state of the store.

```js
{
  type: "BUY_CAKE",
}
```

First let the shopkeeper know that you want to buy a cake. Then the shopkeeper will update the state of the store.

> **3**. To specify how the state tree is transformed by actions, you write pure Reducers.

A reducer is a function that takes the current state and an action as arguments, and returns a new state result.

```js
Reducer = (previousState, action) => newState;
```

```js
const reducer = (state, action) => {
  switch (action.type) {
    case "BUY_CAKE":
      return {
        ...state,
        numberofCakes: state.numberofCakes - 1,
      };
    case "BUY_ICECREAM":
      return {
        ...state,
        numberofIceCreams: state.numberofIceCreams - 1,
      };
    default:
      return state;
  }
};
```
