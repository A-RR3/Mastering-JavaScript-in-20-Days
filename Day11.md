 **Table of Contents**
=====================
* [Introduction](#Introduction)
* [Types](#Types)
* [Coercion](#Coercion)
* [Static Typing](#Static-Typing)
* [Scope](#Scope)
* [TypeScript](#TypeScript)
* [Closure](#Closure)

# Introduction
This README file highlights some important notes on topics from the [third course](https://frontendmasters.com/courses/deep-javascript-v3), with some exercises related to it.

# Types
- Primitive Types: number, boolean, string, null, undefined, object, symbol, BigInt.
- All primitive types, except null, can be tested by the typeof operator. typeof null returns "object", so one has to use === null to test for null.
- Undefined indicates the absence of a value, while null indicates the absence of an object.
- Undefined: It occurs when a variable has been declared but has not been assigned any value.
- Undeclared: It occurs when we try to access any variable that is not initialized or declared.

# Coercion
- Type coercion is the implicit conversion of values from one data type to another (such as strings to numbers).
-  Type coercion occurs when values of different data types are compared in an expression and can errors in your code. 
- Type conversion is similar to type coercion because they both convert values from one data type to another.
- Type coercion is implicit whereas type conversion can be either implicit or explicit.
- Explicit type coercion occurs when the programmer intentionally converts a value from one data type to another using functions like parseInt() or Number().

# Static Typing
-  JS is a dynamically typed languages like Python, Ruby, and JavaScript, type errors are not as easily discoverable because the types of variables are only known at runtime.
-  Flow and TypeScript have emerged as the two main options for enabling static type checking.
-  Sometimes, we don't know what the type of a variable might be. In those cases, we would use the any type.
-  To prevent Type Coercion in JavaScript you can use the strict equality operators (=== and !==) when comparing values.
  
# Scope
- Local Scope : Local variables are created when a function starts, and deleted when the function is completed and cant be accessed outside of a function.
- Block Scope : variables declared using let, cont or var inside a curly brackets cant be accessed from outside the brackets.
- Global variables can be accessed from anywhere in a JavaScript program.
- Global variables are deleted when you close the browser window (or tab).
  

# TypeScript
- JavaScript is a dynamically typed language, meaning that variable types are not declared, but rather are inferred by the interpreter at runtime. While this can make coding more flexible and efficient, it also introduces the problem of type coercion.
- The additional build step in typescript maybe as cons
  
# Closure
- Closure is a form of lexical scoping used to preserve variables from the outer scope of a function in the inner scope of a function. 
- Lexical scoping is the process used to define the scope of a variable by its position in the source code.
-  Closure gives you access to an outer function's scope from an inner function.

# Coding Exercises
### [Week3 Tasks] :(https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week3-day1-tasks/tasks.md)
