# Javascript Methods

- [Javascript Methods](#javascript-methods)
  - [String Methods](#string-methods)
    - [`.length`](#length)
    - [`.slice()` ↑](#slice-)
    - [`.substring()` ↑](#substring-)
    - [`.substr()` ↑](#substr-)
    - [`.replace()` ↑](#replace-)
    - [`.replaceAll()` ↑](#replaceall-)
    - [`.toUpperCase()` ↑](#touppercase-)
    - [`.toLowerCase()` ↑](#tolowercase-)
    - [`.concat()` ↑](#concat-)
    - [`.trim()` ↑](#trim-)
    - [`.trimStart()` ↑](#trimstart-)
    - [`.trimEnd()` ↑](#trimend-)

## String Methods

### `.length`

- The `length` property returns the length of a string:

```js
const str = "Hello World";

console.log(str.length); // 11
```

### `.slice()` [↑](#javascript-methods)

- `slice()` extracts a part of a string and returns the extracted part in a new string.
- The method takes 2 parameters: start position, and end position (end not included).

```js
const str = "Hello World";
let s2 = str.slice(0, 5);
console.log(s2); // "Hello"
```

- If you omit the second parameter, the method will slice out the rest of the string
- If a parameter is negative, the position is counted from the end of the string

### `.substring()` [↑](#javascript-methods)

- `substring()` is similar to `slice()`
- The difference is that start and end values less than 0 are treated as 0 in substring().

```js
let str = "Apple, Banana, Kiwi";
let part = str.substring(7, 13); // "Banana"
```

- If you omit the second parameter, `substring()` will slice out the rest of the string.

### `.substr()` [↑](#javascript-methods)

- `substr()` is similar to `slice()`
- The difference is that the second parameter specifies the **length** of the extracted part

```js
let str = "Apple, Banana, Kiwi";
let part = str.substr(7, 6); // "Banana"
```

- If you omit the second parameter, `substr()` will slice out the rest of the string.
- If the first parameter is negative, the position counts from the end of the string.

```js
let str = "Apple, Banana, Kiwi";
let part = str.substr(-4); // "Kiwi"
```

### `.replace()` [↑](#javascript-methods)

- The `replace()` method replaces a specified value with another value in a string

```js
let str = "Please visit Microsoft!";
let newStr = str.replace("Microsoft", "W3Schools"); // "Please visit W3Schools!"
```

- this method is case sensitive.
- To replace case insensitive, use a regular expression with an /i flag (insensitive)

```js
let text = "Please visit Microsoft!";
let newText = text.replace(/MICROSOFT/i, "W3Schools"); // "Please visit W3Schools!"
```

> 1. **Regular expressions are written without quotes.**
> 2. The replace() method does not change the string it is called on.
> 3. The replace() method returns a new string.
> 4. The replace() method replaces only the first match
> 5. If you want to replace all matches, use a regular expression with the /g flag set.

### `.replaceAll()` [↑](#javascript-methods)

- In 2021, JavaScript introduced the string method `replaceAll()`

```js
text = text.replaceAll("Cats", "Dogs");
text = text.replaceAll("cats", "dogs");
```

- The replaceAll() method allows you to specify a regular expression instead of a string to be replaced.
- If the parameter is a regular expression, the global flag (g) must be set set, otherwise a TypeError is thrown.

```js
text = text.replaceAll(/Cats/g, "Dogs");
text = text.replaceAll(/cats/g, "dogs");
```

> replaceAll() is an ES2021 feature. It is not supported in Internet Explorer.

### `.toUpperCase()` [↑](#javascript-methods)

- A string is converted to upper case with `toUpperCase()`

```js
let text1 = "Hello World!";
let text2 = text1.toUpperCase(); // "HELLO WORLD!"
```

### `.toLowerCase()` [↑](#javascript-methods)

- A string is converted to lower case with `toLowerCase()`

```js
let text1 = "Hello World!";
let text2 = text1.toUpperCase(); // "hello world!"
```

### `.concat()` [↑](#javascript-methods)

- The `concat()` method is used to join two or more strings

```js
let text1 = "Hello";
let text2 = "World";
let text3 = text1.concat(" ", text2); // "Hello World"
```

- The `concat()` method can be used instead of the **plus** operator. These two lines do the same:

```js
text = "Hello" + " " + "World!";
text = "Hello".concat(" ", "World!");
```

> All string methods return a new string. They don't modify the original string.
> Formally said:
> Strings are immutable: Strings cannot be changed, only replaced.

### `.trim()` [↑](#javascript-methods)

- The `trim()` method removes whitespace from both sides of a string

```js
let text1 = "      Hello World!      ";
let text2 = text1.trim(); // "Hello World!"
```

### `.trimStart()` [↑](#javascript-methods)

- ECMAScript 2019 added the String method `trimStart()` to JavaScript.
- The `trimStart()` method works like `trim()`, but removes whitespace only from the start of a string
- JavaScript String trimStart() is supported in all browsers since January 2020

```js
let text1 = "     Hello World!     ";
let text2 = text1.trimStart(); // "Hello World!     "
```

### `.trimEnd()` [↑](#javascript-methods)

- ECMAScript 2019 added the String method `trimEnd()` to JavaScript.
- The `trimEnd()` method works like `trim()`, but removes whitespace only from the end of a string
- JavaScript String trimEnd() is supported in all browsers since January 2020

```js
let text1 = "     Hello World!     ";
let text2 = text1.trimEnd(); // "     Hello World!"
```
