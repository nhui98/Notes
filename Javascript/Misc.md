# Proxy API
- wrapper around an object, that forwards operations on it to the object, optionally trapping some of them.
let proxy = new Proxy(target, {
  /* traps */
});

We can trap:
- Reading (get), writing (set), deleting (deleteProperty) a property (even a non-existing one).
- Calling a function (apply trap).
- The new operator (construct trap).
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy

# Reflect API
- complements Proxy, for any Proxy trap, there’s a Reflect call with same arguments

# Video and audio API

# Location API

# History API

# Navigator API


# Array Buffers

# TextDecoder and TextEncoder

# Blob

# File and FileReader

