# TypeScript: Missing Properties in Object Arguments

This repository demonstrates a subtle bug in TypeScript where the compiler doesn't detect missing properties in objects passed as function arguments.  The code compiles without errors, but at runtime, attempting to access a missing property will throw an error.

## Bug Description
The `printCoord` function expects an object with `x` and `y` properties. However, if an object without one or both of these properties is passed, TypeScript will not raise a compile-time error. This is because TypeScript's type checking doesn't enforce the presence of every property in an object literal unless explicitly declared with `required` in the interface or type.

## How to Reproduce
1. Clone this repository.
2. Compile the code using `tsc bug.ts`.
3. Run the compiled JavaScript code.  You'll see an error at runtime.

## Solution
The solution is to either explicitly declare all object properties as required or use a more robust way to handle optional parameters or partial object types.  See `bugSolution.ts` for example solutions.