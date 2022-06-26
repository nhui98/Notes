# Primitives
number bigInt string boolean null undefined symbol
- primitives except null and undefined provide methods via a temporary wrapper object (e.g. Number, String, ...)

# Numbers
- 6900000, 6_900_000, 6.9e6, 6.9 * 1000000
- .000001, 1e-6, 1 / 1000000
- hex, binary, octal .toString(base)
- Infinity, -Infinity, NaN

*rounding*
(Math) .floor() .ceil() .round() .trunc()
(num) .toFixed()

*isNaN & isFinite*
isNan() isFinite()
NaN === NaN           //false
Object.is(NaN, NaN)   //true
0 === -0              //true
Object.is(0, -0)      //false

*Conversion*
Number() + parseInt() parseFloat()

*Other Math Functions*
.random() .max() .min() .pow()

# Strings
- strings are array of characters, str[0]
- template strings
- special/escaped characters, unicode symbols
- strings are immutable
- strings are compared by their unicode chars 
  .codePointAt() 
  .fromCodePoint()  
- str1.localeCompare(str2)  //better way to compare
  returns negative number if str less than str2, positive if greater, and 0 if equal

*Accessing characters*
for (let char of string) {}

(properties)  .length
(methods)     .charAt() .toUpperCase() .lowerCase()
              .indexOf() .lastIndexOf()
              .includes() .startsWith() .endsWith()
              .trim() .split()
              .substring() .slice() .substr()

# Arrays
- arr[], new Array(), arr[][]

*type check array*
Array.isArray()       // typeof [] gives "object"

*get last element*
- arr[arr.length -1] 
- arr.at(-1)

*methods*
(add items)         .pop() .push() 
                    .shift() .unshift()
(remove items)      .splice() 
(new array)         .slice() .concat()
(searching)         .indexOf()/lastIndexOf() .findIndexOf()/findLastIndex() .includes()
(transform)         .sort() .reverse() .split() .join()
(convert to string) .toString() String(arr) //returns a comma-separated list of elements

*iterating*
for for..of

*advanced array methods*
.find() .some() .every()
.fill() .copyWithin() .flat/flatMap()
.map() 
.filter()
.reduce() .reduceRight()

# Iterables
- objects that can be used in for..of are iterables
- to make an object iterable:
1. implement the method named Symbol.Iterator
2. this method must have a method named next()
3. next() returns an object {done: Boolean, value: any}

- Objects that have indexed properties and length are array-like
- Array.from(obj) //makes a real array from an iterable or array-like obj

# HashMap & HashSet
*Map*
- objects but keys can be of any type
- new Map(), new Map(//arr of key value pairs)

(properties)  .size
(methods)     .set(key, value) .get(key)
              .has(key)
              .delete(key) .clear()
(iteration)   .keys() .values() .entries()
(object -> map)   newMap(Object.entries(obj))
(map -> object)   Object.fromEntries(map.entries())

*Set*
- array but values are unique
- new Set(), new Set(iterable)

(properties)  .size
(methods)     .add(value) 
              .has(value)
              .delete(value) .clear()
(iteration)   .forEach() for..of 
              .keys() .values() .entries()

*WeakMap & WeakSet*
- new WeakMap() //can only use objects for keys
- only supports .get() .set() .delete() .has()

- new WeakSet() //values can only be objects
- only supports .add() .delete() .has()

- good for additional storage/caching, can be garbage collected very easily

# Destructuring
- array destructuring, [val1, val2] = arr, [...arr]
- object destructuring, {prop1, prop2} = obj, [...obj]
- nested destructuring, {prop1, obj: {p1, p2}, arr: [v1, v2]} = obj

# Date & Time
- new Date(), new Date(year, month, date, hours, minutes, seconds, ms)

*get time and date relative to local time zone*
.getFullYear() .getMonth() .getDate() .getDay() .getHours() .getMinutes() .getSeconds() .getMilliseconds()
- getUTC for variant all the above methods

.getTime() .getTimezoneOffset()

*set time and date*
setFullYear(year, [month], [date])
setMonth(month, [date])
setDate(date)
setHours(hour, [min], [sec], [ms])
setMinutes(min, [sec], [ms])
setSeconds(sec, [ms])
setMilliseconds(ms)
- setUTC variant for all the above methods

setTime(milliseconds) 

*get current date and time*
Date.now()

*string to date*
Date.parse(str) //format YYYY-MM-DDTHH:mm:ss.sss or shorter variants

# JSON
JSON.Stringify()
- skips methods, symbols, undefined properties
- fails when circular reference

JSON.stringify(value, replacer, space)
- A value to encode.
- Array of properties to encode or a mapping function function(key, value)
- Amount of space to use for formatting

JSON.parse()
JSON.parse(value, reviver)