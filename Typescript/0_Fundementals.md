# Setup
npm i -D typescript

tsc --init
tsc                        //compile all ts files
tsc filename.ts --watch

# Compiler comments
// @ts-nocheck              //check this file
// @ts-check              
// @ts-ignore               //ignore next line
// @ts-expect-error         //expect error on next line

# Operators
?? (nullish coalescing)    
?. (optional chaining)
?  (optional property)
!  (non-null assertion)     //we're sure the value is defined
&&=                         //assign value if truthy
||=                         //assign value if falsy
??=                         //assign value if null or undefined

# Conditionals
- keyof
- extends
- ?:
- readonly

# Type Guards
- is
- typeof
- instanceof
- in

# Assertion
- as type | <type>value
- as const | <const>value

