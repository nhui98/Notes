# Prototypal inheritance
- all objects have [[Prototype]] property which is null or references a prototype
- all properties and methods are inherited from the referenced prototype
- accessed with obj.__proto__
- obj.prototype exists on all objects and is null or an object
- when an object is created using this obj with the new keyword, it sets the new objects [[Prototype]] to obj.prototype

- for..in loops through its own properties as well as inherited properties
- obj.hasOwnProperty(key)

*setting and getting prototypes*
- use these instead of directly manipulating obj.__proto__
Object.create(proto, [descriptors]) //create empty object with [[Prototype]] set to given proto, and optional property descriptors.
Object.getPrototypeOf(obj) – returns the [[Prototype]] of obj.
Object.setPrototypeOf(obj, proto) – sets the [[Prototype]] of obj to proto.

*cloning an object*
Object.create(Object.getPrototypeOf(obj), Object.getOwnPropertyDescriptors(obj));

# Classes
- class methods have enumerable set to false 

*inheritance*
class Child extends Parent {}
- sets Child.prototype.[[Prototype]] to Parent.prototype

- can override methods, call parent method with super.method()
- override constructor, call super() in Child constructor before using this
- Methods remember their class/object in the internal [[HomeObject]] property. That’s how super resolves parent methods

*static*
- Static methods are used for the functionality that belongs to the class “as a whole”. It doesn’t relate to a concrete class instance
- Static properties are used when we’d like to store class-level data, also not bound to an instance.

*private & protected*
- _field, #field
- encapsulation, hiding internal implementation details

*Class Checking*
obj instanceof Class

*Mixins*
- objects can only inherit from one parent
- use a mixin: generic object that contians methods for other classes
- Object.assign(parent.prototype, mixinObj)