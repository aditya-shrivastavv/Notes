# Javascript Deep Dive

- Three Pillars of JS
  - Types
    - primitive types
    - abstract operations
    - coercion
    - equality
  - Scope
    - nested scope
    - hoisting
    - closure
    - modules
  - Object
    - this
    - class
    - prototypes

1. "In JavaScript, everything is an object." - **False**
   - JS has primitive types too like... undefined, string, number, boolean, symbol, bigint, null etc.
2. `typeof` operator always returns a string.
3. undefined, undeclared and uninitialized are all different things. There is a historical bug in JS where `typof` operator returns **undefined** even for the undeclared variables.
4. Fundamental Objects are objects which are derived from primitive types.
   - Use `new`:
     - Object()
     - Array()
     - Function()
     - Date()
     - RegExp()
     - Error()
   - not recommended:
     - String()
     - Number()
     - Boolean()
     - these should only be used as functions not as a constructor because there is no use.
5. The `+` operator is overloaded, if it is used in between all numbers it performs arithemetic operation but, if any of them is a string it does string concatenation. coerecion takes place internally.
6. `+numericalString` converts it into a number.
7. you have to adopt a coding style that makes value types plain and obvious
8. the most important difference between `==` and `===` is - in double equals comparison if the types of both values are the same then triple equal is used for final comparison.
   - the `==` operation prefers numeric comparitson.
9. `==` Summary:
   - if types are same: `===`
   - if null or undefind: equal
   - if non primitive: ToPrimitive
   - prefers: toNumber
10. if we try to assign a value to an undeclared variable that variable gets declared automatically into the global scope. This is known as Dynamic Global Variables. You should never use it though, cause it might unknowingly pollutes the global scope.
