# Error Handling
try {} catch (err) {} finally {}

*error object*
- message – the human-readable error message.
- name – the string with error name (error constructor name).
- stack (non-standard, but well-supported) – the stack at the moment of error creation.

*throw custom errors*
throw new Error()
- can extend/inherit from Error and create our own error objects

*rethrowing errors*
- in catch block, we can handle specific errors by using instanceof
- and throwing errors we dont want to handle for an outer block's catch?

*global catch*
window.onerror = function(messaeg, url, line, col, error) {}

# Callback
- callback hell

# Promises
new Promise((resolve, reject) => {
  //eventually resolve a value
  //or reject with an error
  //a promise will always have a state(pending/fulfilled/rejected) and the result(value/error)
})
.then((value) => {})
.finally(() => {}) //does get args, return is ignored, if error is thrown inside it goes to nearest error handler
.catch(err => {})

- there is an invisble trycatch that wraps a promise handler, that automatically rejects if it catches an error

*Promise Chaining*
.then((value) => //returns a promise allowing .then chaining)
.then(handler)

*Promise API*
Promise.all([promise1, promise2])
- executes promises in parallel, if one promise rejects then the Promise.all rejects
- returns [resolvedValue1, resolvedValue2]

Promise.allSettled()
- waits for all promises to settle regardless of result
- returns [{status: 'fulfilled', value: ...response...}, {status: 'rejected', reason: ...error object...}, ...]

Promise.race()
- waits only for the first settled promise whether if it resolves or rejects

Promise.any()
- waits only for the first resolved promise
- rejects if all promises are rejected

Promise.resolve() / Promise.reject()

# Async/Await
An async function:
1. always returns a promise
2. allows await to be used in it

- await is used before a promise
- wrap in try catch for error handling

# Generators
function* fnName() {}
- each yield returns {value: ..., done: true/false}
- outer code and the generator may exchange results via next/yield calls.

- generators are iterables

*async iterables*
1. Use Symbol.asyncIterator instead of Symbol.iterator
2. next() method should return a promise ie. use async next()
3. iterate over object: for await (let item of iterable)

*async generators*
async function * fnName() { await...yield...}
- returns a promise