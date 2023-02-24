# 28 Javascript Array Methods

- [28 Javascript Array Methods](#28-javascript-array-methods)
  - [Comman](#comman)
    - [`.length` ↑](#length-)
  - [Core](#core)
    - [1. `.concat()` ↑](#1-concat-)
    - [2. `.copyWithin()` ↑](#2-copywithin-)
    - [3. `.entries()` ↑](#3-entries-)
    - [4. `.every()` ↑](#4-every-)
    - [5. `.fill()` ↑](#5-fill-)
    - [6. `.filter()` ↑](#6-filter-)
    - [7. `.find()` ↑](#7-find-)
    - [8. `.findIndex()` ↑](#8-findindex-)
    - [9. `.forEach()` ↑](#9-foreach-)
    - [10. `Array.from()` ↑](#10-arrayfrom-)

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

console.log(numbers.concat(characters));
// [1, 2, 3, 'a', 'b', 'c']

console.log(numbers.concat(characters, booleans));
// [1, 2, 3, 'a', 'b', 'c', true, false]

console.log(numbers.concat(characters, 24, "John", { x: 12, y: 13 }));
// [1, 2, 3, 'a', 'b', 'c', 24, 'John', {x: 12, y: 13}]
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
console.log(arr1.copyWithin(2));
// ['a', 'b', 'a', 'b', 'c', 'd', 'e', 1]

// copy elements from index 4 to last index to index 2
console.log(arr2.copyWithin(2, 4));
// ['a', 'b', 'e', 1, 2, 3, 'e', 1]

// copy elements from index 4 to index 6 to index 2
console.log(arr3.copyWithin(2, 4, 6));
// ['a', 'b', 'e', 1, 'e', 1, 2, 3]
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
console.log(iterator1.next()); // { value: [0, 'a'], done: false }
console.log(iterator1.next().value); // [1, 'b']
console.log(iterator1.next().value); // [2, 'c']

// using for...of loop
const iterator2 = arr.entries();
for (const [index, value] of iterator2) {
  console.log(index, value);
}
// 0, a
// 1, b
// 2, c
// 3, d
// 4, e
```

### 4. `.every()` [↑](#28-javascript-array-methods)

The `every()` method in javascript executes a function for each element in the array and returns true if the function returns true for all elements.

- The original array is not modified by this method.

**Syntax**:

```js
arr.every(callback(currentValue, index, arr), thisArg);
```

- You can define the callback function within the method or you can define it outside the method.

- The callback function takes three arguments:
  - `currentValue`: defines the current element in the array.
  - `index` (optional): defines the index of the current element in the array.
  - `arr` (optional): defines the array.

```js
const arr1 = [1, 2, 3, 4, 5];
const arr2 = [22, 42, 86, 100, 4];

function isEven(num) {
  return num % 2 === 0;
}

console.log(arr1.every(isEven)); // false
console.log(arr2.every(isEven)); // true
```

### 5. `.fill()` [↑](#28-javascript-array-methods)

The `fill()` method in javascript returns a modified array by filling a specified index with the specified value.

- The original array is not modified by the `fill()` method.

**Syntax**:

```js
arr.fill(value);
arr.fill(value, start);
arr.fill(value, start, end);
```

The fill() method accepts 3 arguments:

- `value`: Value to be filled
- `start`(optional): Index from where the filling has to start Default value is 0.
- `end`(optional): Index where the filling is to be stopped.

**Example**:

```js
const arr = ["a", "a", "a", "a", "a", "a", "a"];

// fill the whole array with "b"
console.log(arr.fill("b"));
// ['b', 'b', 'b', 'b', 'b', 'b', 'b']

// fill the array from index 2 to last with "c"
console.log(arr.fill("c", 2));
// ['b', 'b', 'c', 'c', 'c', 'c', 'c']

// fill the array from index 4 to index 6 with "d"
console.log(arr.fill("d", 4, 6));
// ['b', 'b', 'c', 'c', 'd', 'd', 'c']
```

- This method can be used when you create an array of a specified size and you want to fill the array with a particular value.

```js
const arr = new Array(10).fill("a");
console.log(arr);
// ['a', 'a', 'a', 'a', 'a', 'a', 'a', 'a', 'a', 'a']
```

### 6. `.filter()` [↑](#28-javascript-array-methods)

The `filter()` method in javascript is used to create a new array with the elements of the same array if elements pass a certain condition.

- The `filter()` methods accept a callback function as an argument.
- The callback function returns **true** or **false** after checking some conditions over each and every element. If true is returned then that element is added to the new array, else discarded.
- Finally, a new array is returned with those added elements.

**Syntax**:

```js
arr.filter(callback(currentValue, index, arr), thisArg)
The argument currentValue is necessary and index and arr are optional.
```

**Example**:

```js
const arr = [10, 12, 5, 15, 2, 32, 20, -5, 23];

// create a new array with all the elements greater than 10
console.log(arr.filter((element) => element > 10));
// [12, 15, 32, 20, 23]

// array with only even numbers
console.log(arr.filter((element) => element % 2 === 0));
// [10, 12, 2, 32, 20]
```

### 7. `.find()` [↑](#28-javascript-array-methods)

The `find()` method in javascript is returned the first value of the array elements which satisfies the provided condition.

- The `find()` method accepts a callback function where you can define the condition.
- The callback function returns **true** or **false** after checking some conditions over each and every element. If true is returned then the element is returned, else the next element is checked.
- Finally, the first element which satisfies the condition is returned.

**Syntax**:

```js
arr.find(callback(currentValue, index, arr), thisArg);
```

**Example**:

```js
const arr = [1, 10, 2, 25, 5, 15];

// method return the first element which is greater than 10
console.log(arr.find((element) => element > 10));
// 25
```

- If nothing is found then undefined is returned.
- The `find()` method does not return the index of the element which satisfies the condition to get index use `findIndex()` method.

### 8. `.findIndex()` [↑](#28-javascript-array-methods)

The `findIndex()` method is the same as `find()` but it returns the index value of the element, not the value itself.

- If no such element exists then returns -1.
- The `findIndex()` method accepts a callback function where you can define the condition.

**Syntax**:

```js
arr.findIndex(callback(currentValue, index, arr), thisArg)
Let's find the index of first element which is greater than 10.
```

**Example**:

```js
const arr = [1, 10, 2, 25, 5, 15];

// method return the index of first element which is greater than 10
console.log(arr.findIndex((element) => element > 10));
// 3
```

### 9. `.forEach()` [↑](#28-javascript-array-methods)

The `forEach()` method in javascript is used to iterate over each and every element of the array and execute a function for all elements.

- It accepts a callback function as an argument.

**Syntax**:

```js
arr.forEach(callback(currentValue, index, arr), thisArg);
```

The callback function accepts three arguments:

- `currentValue`: is the current element of the array.
- `index`: is the index of the current element.
- `arr`: is the array itself.

**Example**:

```js
const arr = [10, 12, 37, 24, 65];

function print(element, index) {
  console.log(element + " is at index " + index);
}

arr.forEach(print);

// 10 is at index 0
// 12 is at index 1
// 37 is at index 2
// 24 is at index 3
// 65 is at index 4
```

### 10. `Array.from()` [↑](#28-javascript-array-methods)

The `Array.from()` method in javascript is used to convert an array like object to an array.

- What do we mean by an array like object?
  - An array like object is an object which has a length property. Example: string, arguments, NodeList, HTMLCollection, etc.
  - To convert these objects to a proper array pass the object as an argument to the Array.from() method.

**Syntax**:

```js
Array.from(arrayLike);
```

- The Array.from() method returns a new array and does not change the original array.

**Example**:

```js
const alphabets = "abcdefghijklmnopqrstuvwxyz";

// converting string to array
const arr = Array.from(alphabets);
console.log(arr);
// ['a', 'b', 'c', ... 'z']

const obj = {
  0: "a",
  1: "b",
  2: "c",
  length: 3,
};
// converting object to array
const arr2 = Array.from(obj);
console.log(arr2);
// ['a', 'b', 'c']
```
