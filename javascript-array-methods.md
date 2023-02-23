# 28 Javascript Array Methods

- [28 Javascript Array Methods](#28-javascript-array-methods)
  - [Comman](#comman)
    - [`.length` ↑](#length-)
  - [Core](#core)
    - [1. `.concat()` ↑](#1-concat-)
    - [2. `.copyWithin()` ↑](#2-copywithin-)
    - [3. `.entries()` ↑](#3-entries-)

## Comman

### `.length` [↑](#28-javascript-array-methods)

```js
const arr = [1, 2, 3, 4, 5];
console.log(arr.length); // 5
```

## Core

### 1. `.concat()` [↑](#28-javascript-array-methods)

The `concat()` array method in javascript is used to merge 2 or more arrays or values into a single array.

- The `concat()` method does not change the original array but returns a new array by merging them.

**Syntax**:

```js
var newArray = arr.concat(arg1, arg2, ...)
```

**Example**:

```js
const numbers = [1, 2, 3];
const characters = ["a", "b", "c"];
const booleans = [true, false];

console.log(numbers.concat(characters)); // [1, 2, 3, 'a', 'b', 'c']
console.log(numbers.concat(characters, booleans)); // [1, 2, 3, 'a', 'b', 'c', true, false]
console.log(numbers.concat(characters, 24, "John", { x: 12, y: 13 })); // [1, 2, 3, 'a', 'b', 'c', 24, 'John', {x: 12, y: 13}]
```

- Apart from concat() method, you can also spread operator (...) to merge multiple arrays and values into a single array.

```js
const numbers = [1, 2, 3];
const characters = ["a", "b", "c"];
const booleans = [true, false];

console.log([...numbers, ...characters]); // [1, 2, 3, 'a', 'b', 'c']
console.log([...numbers, ...characters, ...booleans]); // [1, 2, 3, 'a', 'b', 'c', true, false]
console.log([...numbers, 24, "John"]); // [1, 2, 3, 24, 'John']
```

### 2. `.copyWithin()` [↑](#28-javascript-array-methods)

The `copyWithIn()` method in javascript copies a part of the same array within the same calling array.

- This method modifies elements of the original array but the length of the array is not modified.

**Syntax**:

```js
arr.copyWithIn(targetIndex);
arr.copyWithIn(targetIndex, startIndex);
arr.copyWithIn(targetIndex, startIndex, endIndex);
```

- `targetIndex`: from where a copy of the element should starts
- `startIndex` (_optional_): from where the method starts copying elements. Default value is 0.
- `endIndex` (_optional_): index at which method stops copying the element. Default value is the last index.

```js
const arr1 = ["a", "b", "c", "d", "e", 1, 2, 3];
const arr2 = ["a", "b", "c", "d", "e", 1, 2, 3];
const arr3 = ["a", "b", "c", "d", "e", 1, 2, 3];

// copy elements from index 0 to last index to index 2
console.log(arr1.copyWithin(2)); // ['a', 'b', 'a', 'b', 'c', 'd', 'e', 1]

// copy elements from index 4 to last index to index 2
console.log(arr2.copyWithin(2, 4)); // ['a', 'b', 'e', 1, 2, 3, 'e', 1]

// copy elements from index 4 to index 6 to index 2
console.log(arr3.copyWithin(2, 4, 6)); // ['a', 'b', 'e', 1, 'e', 1, 2, 3]
```

> When you use the negative index, the method starts counting from the end of the array. i.e -1 is the last index, -2 is the second last index, and so on.

### 3. `.entries()` [↑](#28-javascript-array-methods)

The `entries()` method in javascript returns a new Array Iterator object that contains the key/value pairs for each index in the array.

- The `entries()` method does not change the **original** array but returns a **new array** iterator object.
- This iterator can be used to get the next element in the array by calling the next() method on the iterator object.

**Syntax**:

```js
arr.entries();
```

Here the entries() method does not take any argument.

**Example**:

```js
const arr = ["a", "b", "c", "d", "e"];
const iterator1 = arr.entries();
console.log(iterator1.next());
console.log(iterator1.next().value);
console.log(iterator1.next().value);

// using for...of loop
const iterator2 = arr.entries();
for (const [index, value] of iterator2) {
  console.log(index, value);
}
```
