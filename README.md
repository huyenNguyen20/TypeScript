"# TypeScript" 
## Set Up
* Node Environment
* TypeScript Compiler such as typescript package: To compile TS code to JS code
* Code Editor
## Running Script for .ts file
* `tsc app.ts` ; then, `node app.js` for  `typescript` package
* `ts-node app.ts` for `ts-node` package
## Why TypeScript
* JavaScript is dynamically typed. It offers flexibility but also creates many problems.
* TypeScript adds an optional type system to JavaScript to solve these problems.
## Types in TypeScript
* In general, every value in TypeScript has a type. A type is a label that describes the properties and methods that a value has. TypeScript compiler uses types to analyze your code for hunting bugs and errors.
### 2 categories of TypeScript Types
* Primitive Types: `string`, `number`, `boolean`, `null`, `undefined`, `symbol`
* Object Types: `function`, `array`, `classes`
### Type Annotations
* It is used to explicitly specify types for identifiers such variables, functions, objects, etc.
Syntax
```
let variableName: type;
let variableName: type = value;
const constantName: type = value;
```