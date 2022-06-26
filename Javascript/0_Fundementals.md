# JS
- dynamically typed, single threaded, asynchronous, non-blocking
- event loop, heap, call stack, microtask queue, callback queue, 

# Strict mode
"use strict"

# Variables
var - local/global scope
let, const - block scope

# Data Types
number bigInt string boolean null undefined object symbol

typeof
- returns "object" for null

# Type Conversion
*string conversion*
String() .toString()
*numeric conversion*
Number() + parseInt() parseFloat()
*Boolean conversion*
Boolean !!

# Operators
Arithmetic    + - * / % ++ -- ** 
Assignment    = += -= *= /= %= **=
Comparison    == != === !== > >= < <=
String        +
Ternary       ? :
Logical       && || ?? !
Comma         ,

# null and undefined
null === undefined  // false
null == undefined   // true
null > 0            // false
null == 0           // false
null >= 0           // true

# Conditional Statements
Falsy - false, undefined, null, 0, NaN, ""

if...elseif...else
? :
switch...case
||  *if false then
&&  *if true then
??  *if null then

# Loops
for
for...in
for...of
do...while
while
label, break, continue

# Good Comments (JSDoc)
/**
 * Brief Description.
 * @param {number} x Short Description.
 * @param {number} n Short Description.
 * @return {number} x Short Description.
 */

# Transpiler
- Babel, Typescript

# Polyfills
- script that updates/adds new functions to “fill in” the gap and add missing implementations.
- core js, polyfill.io

# Garbage Collection
- unreferenced obj or unreachable code will be garbage collected
