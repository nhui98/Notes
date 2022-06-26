# Modules
1. A module is a file. To make import/export work, browsers need <script type="module">
  - Deferred by default.
  - To load external scripts from another origin (domain/protocol/port), CORS headers are needed
2. Modules have their own, local top-level scope and interchange functionality via import/export.
3. Modules always use strict.
4. Module code is executed only once. Exports are created once and shared between importers.

# Export 
1. Before declaration of a class/function/…:
export [default] class/function/variable ...
2. Standalone export:
export {x [as y], ...}.
3. Re-export:
export {x [as y], ...} from "module"
export * from "module" (doesn’t re-export default).
export {default [as y]} from "module" (re-export default).

# Import
1. Importing named exports:
import {x [as y], ...} from "module"
2. Importing the default export:
import x from "module"
import {default as x} from "module"
3. Import all:
import * as obj from "module"
Import the module (its code runs), but do not assign any of its exports to variables:
import "module"

# Dynamic Imports
- import(module) returns a promise that resolves into a module object that contains all its exports.
- await import(module)