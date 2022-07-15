# Primitives
any null undefined void never unknown
string number boolean bigint symbol

# Built in JS Objects
Date Error Array Map Set Regexp Promise
- avoid: Object String Number Boolean

# Array and Tuples
- type[] | Array<Type>

# Object
- With aribitary string properties: {[key: Type] : Type}
- get fn(): type
- set fn(): type

# Enum

# Literal Types

# Functions
- (arg1: Type, argN: Type) => Type | { (arg1: Type, argN: Type): Type }
- Constructor: new () => ConstructedType | { new (): ConstructedType; }
- this typing: function fn(this: Foo, arg1: string) {}
- Overloads:
function fn(a: string): number;
function fn(a: number): string;
function fn(a: string | number): string | number {...}

# Union and Intersection

# Type Alias

# Interface
- can extend mutiple objects

# Class
- extend one parent class, super
- implements many interfaces
- private, protected, static
- this                                      //refers dynamically to the type of the current class
- abstract class and properties             //cant be instantiated, abstract properties need to be implemented

# Generics
- function fn<T>():Type {} | <T>(): Type
- interface name<T> {}
- class name<T> {}
- type name<T> = 