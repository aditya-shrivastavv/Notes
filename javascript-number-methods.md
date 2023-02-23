# Javascript Number Methods

- [Javascript Number Methods](#javascript-number-methods)
  - [Common](#common)
    - [`.toString()`](#tostring)
    - [`.toExponential()`](#toexponential)
    - [`.toFixed()`](#tofixed)
    - [`.toPrecision()`](#toprecision)
    - [`.valueOf()`](#valueof)
  - [Type Conversion](#type-conversion)
    - [`Number()`](#number)
    - [`parseInt()`](#parseint)
    - [`parseFloat()`](#parsefloat)
  - [Number object methods](#number-object-methods)
    - [`Number.isInteger()`](#numberisinteger)
    - [`Number.isSafeInteger()`](#numberissafeinteger)
    - [`Number.isNaN()`](#numberisnan)
    - [`Number.isFinite()`](#numberisfinite)
    - [`Number.parseFloat()`](#numberparsefloat)
    - [`Number.parseInt()`](#numberparseint)

## Common

### `.toString()`

- The `toString()` method returns a number as a string.

```js
let x = 123;
x.toString(); // "123"
```

### `.toExponential()`

- `toExponential()` returns a string, with a number rounded and written using exponential notation.

```js
let x = 9.656;
x.toExponential(2); // "9.66e+0"
x.toExponential(4); // "9.6560e+0"
x.toExponential(6); // "9.656000e+0"
```

### `.toFixed()`

- `toFixed()` returns a string, with the number written with a specified number of decimals.

```js
let x = 9.656;
x.toFixed(0); // "10"
x.toFixed(2); // "9.66"
x.toFixed(4); // "9.6560"
x.toFixed(6); // "9.656000"
```

> toFixed(2) is perfect for working with money.

### `.toPrecision()`

- `toPrecision()` returns a string, with a number written with a specified length

```js
let x = 9.656;
x.toPrecision(); // "9.656"
x.toPrecision(2); // "9.7"
x.toPrecision(4); // "9.656"
x.toPrecision(6); // "9.65600"
```

> The difference between `toFixed` and `toPrecision` is that `toFixed(n)` provides n length after the decimal point; `toPrecision(x)` provides x total length.

### `.valueOf()`

- `valueOf()` returns a number as a number.

```js
let x = 123;
x.valueOf(); // 123
(123).valueOf(); // 123
(100 + 23).valueOf(); // 123
```

> In JavaScript, a number can be a primitive value (typeof = number) or an object (typeof = object).
> The valueOf() method is used internally in JavaScript to convert Number objects to primitive values.
> **There is no reason to use it in your code.**

## Type Conversion

### `Number()`

- `Number()` can be used as a function to convert variables to numbers.

```js
Number("3.14"); // 3.14
Number(" "); // 0
Number(""); // 0
Number("99 88"); // NaN
Number("99,88"); // NaN
Number("John"); // NaN

Number(new Date("1970-01-01")); // 0
Number(new Date("1970-01-02")); // 86400000
Number(new Date("2023-02-22")); // 1672505600000
```

> The `Date()` method returns the number of milliseconds since 1.1.1970

### `parseInt()`

- `parseInt()` parses a string and returns an integer.

```js
parseInt("10"); // 10
parseInt("10.33"); // 10
parseInt("10 20 30"); // 10
parseInt("10 years"); // 10
parseInt("years 10"); // NaN
```

> If the number cannot be converted, NaN (Not a Number) is returned.

### `parseFloat()`

- `parseFloat()` parses a string and returns a floating point number.

```js
parseFloat("10"); // 10
parseFloat("10.33"); // 10.33
parseFloat("10 20 30"); // 10
parseFloat("10 years"); // 10
parseFloat("years 10"); // NaN
```

## Number object methods

### `Number.isInteger()`

- The Number.isInteger() method returns true if the argument is an integer.

```js
Number.isInteger(0); // true
Number.isInteger(1); // true
Number.isInteger(-100000); // true
Number.isInteger(10.0); // true
Number.isInteger(10.5); // false
Number.isInteger("hehe"); // false
```

### `Number.isSafeInteger()`

- A safe integer is an integer that can be exactly represented as a double precision number.
- The Number.isSafeInteger() method returns true if the argument is a safe integer.

```js
Number.isSafeInteger(10); // true
Number.isSafeInteger(12345678901234567890); // false
```

> Safe integers are all integers from -(2^53 - 1) to +(2^53 - 1).
> This is safe: 9007199254740991. This is not safe: 9007199254740992.

### `Number.isNaN()`

- The Number.isNaN() method determines whether a value is NaN or not.

```js
Number.isNaN(NaN); // true
Number.isNaN(10); // false
Number.isNaN("10"); // false
Number.isNaN(true); // false
Number.isNaN(10 / "H"); // true
Number.isNaN("true" / 0); // true
Number.isNaN("true" / "true"); // true
```

### `Number.isFinite()`

- The Number.isFinite() method determines whether the passed value is a finite number.

```js
Number.isFinite(0); // true
Number.isFinite(2e64); // true
Number.isFinite(Infinity); // false
Number.isFinite(NaN); // false
Number.isFinite(-Infinity); // false
Number.isFinite("0"); // false
```

### `Number.parseFloat()`

- Number.parseFloat() parses a string and returns a number.
- Spaces are allowed. Only the first number is returned:

```js
Number.parseFloat("10"); // 10
Number.parseFloat("10.33"); // 10.33
Number.parseFloat("10 20 30"); // 10
Number.parseFloat("10 years"); // 10
Number.parseFloat("years 10"); // NaN
```

> Note
> The Number methods Number.parseInt() and Number.parseFloat() are the same as the
> Global methods parseInt() and parseFloat().
> The purpose is modularization of globals (to make it easier to use the same JavaScript code outside the browser).

### `Number.parseInt()`

- same as [`parseInt()`](#parseint)
