# Functions
- function declaration            //can be called earlier than it is defined 
- function expression             //created when the execution reaches it and is usable only from that moment
- arrow functions                 //do not have its own this keyword 
- new Function (arg1, arg2, ...argN, functionBody);  //functions created this way only have access to global lexical scope
- callback functions
- IIFE  (function() {})()
- default params, rest params
- arguments variable

# This
all functions/methods have a this, its value is defined at run time when the function is called
- method - refers to owner object
- alone/function - refers to global object
- function(strict mode) - undefined
- event - refers to element that received the event

# Call, Bind, Apply
- .call(this, arg1, arg2, ...)
- .apply(this, [arg1, arg2, ...])
- .bind(this, arg1, arg2, ...) 

# Closure
- all function get a hidden property [[Environment]] (lexical environment) which references the outer lexical environment / global environment
- so inner, nested functions can access args and variables of the outer function 
- even if the outer function expires or goes out of scope because theres still a reference to [[Environment]] (lexical environment)

# Execution Context
- internal data structure containing details about the execution of a function: where the control flow is now, the current variables, the value of this

# Recursion

# Global Object
- window(browser), global(Node)
- can add global properties 
- can check if a feature exists and add a polyfill, if !window.Promise {...}

# Scheduling
setTimeout(func, delay, ...args)
setInterval(func, delay, ...args)
clearTimeout/clearInterval

- places the function call in a callback queue which waits until the callstack is empty until resolving

# Decorators
- a wrapper around a function that alters its behaviour
