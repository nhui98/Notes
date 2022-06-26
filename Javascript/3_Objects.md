# Objects / HashTables
- keys are either strings, numbers or symbols
- square bracket notation for property access and computed properties
- integer keys are ordered, rest are by insertion order
- passed by reference
- methods - functions in an object, can reference the object as this

*delete property*
delete

*check if property exists*
"key" in object

*Comparing two values*
Object.is(value1, value2)
- same as === but more reliable for edge cases

*looping over keys in object*
- Object.keys(obj)
- Object.values(obj)
- Object.entries(obj)
- for (key in object) {}

*Cloning and merging*
- Object.assign(newObj, obj, obj2, ...)
- clone = {...obj}
- _.cloneDeep(obj) for nested objects

*Constructor function*
- When a function is executed with new, it does the following steps:
1. A new empty object is created and assigned to this.
2. The function body executes. Usually it modifies this, adds new properties to it.
3. The value of this is returned.

- if an object is returned in the constructor function, that will override this

*Optional chaining*
obj?.prop       //returns prop exists, otherwise undefined.
obj?.[prop]     //returns obj[prop] exists, otherwise undefined.
obj.method?.()  //calls obj.method() if exists, otherwise returns undefined.

# Object Properties Configuration
- object properties have additional special attributes called flags
1. writable       //can be changed?
2. enumerable     //shows in loops?
3. configurable   //can be deleted? can these flags be modified?
- Object.getOwnPropertyDescriptor(obj, propertyName) / Object.getOwnPropertyDescriptors(obj))
- Object.defineProperty(obj, propertyName, descriptor) / Object.defineProperties(obj, descriptors)

*Sealing an object globally*
Object.preventExtensions(obj)/isExtensible(obj)   //Forbids the addition of new properties to the object.
Object.seal(obj)/.isSealed(obj)                   //Sets configurable: false
Object.freeze(obj)/.isFrozen(obj)                 //Sets configurable: false, writable: false

*Getters and Setters*

# Symbols
- primitive type for unique identifiers
- does not participate in Object.keys() and for in loop
Symbol("optional description name")

*Global Symbols*
Symbol.for(key)
Symbol.ketFor(sym)