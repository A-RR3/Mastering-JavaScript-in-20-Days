**Table of Contents**
=====================
* [Introduction](#Introduction)
* [Expressions](#Expressions)
* [Arrays](#Arrays)
* [Objects](#Objects)

# Introduction
This README file highlights some important notes from the [first course](https://frontendmasters.com/courses/javascript-first-steps/) on expressions, arrays, objects


# Expressions
## Definition
An expression is a statement having minimum of two numbers, or variables, or both and an operator connecting them

## Examples On Expressions
- "frontend" + "masters"
- 5 > 4 !== 3 > 4
- 4/3*10

# Arrays
## Definition
- Arrays let us keep multiple values together in a single collection
- Every array element has an index
- we type array.indexof("value") to find what number correspons t0 some value
- we type array.includes("value") to check if an array includes that value
- Manipulate array items by pushing and popping items
- an Array can be empty and can have multiple datatypes

## Usefull Array Methods
- sort(): sorts alphabet and numbers in an ascending order
- join(" "): joins arrays elements with a space between
- [1,2,3].concate([4,5]) returns [1,2,3,4,5] , but contact and push don't work the same, because when pushing [4,5], a whole item of type array will be added to the first array

## Mutable VS Immutable
- mutable data can be edited (e.g: arrays)
- immutable data always stays the same (e.g: strings anf other primitives)

## Code Examples
```javascript
// Example 1: push
let numbers1 =[1,2,3]
let result1= numbers1.push(4)

output:
numbers1: [1,2,3,4]
result1: 4


// Example 2: concat
let numbers2 =[1,2,3]
let result2= numbers2.concat([4])

output:
numbers2: [1,2,3]
result2: [1,2,3,4]

//Example 3: What happens when we use const with mutable value like an array
const operands =[4,6];
const sum = operands[0]+operands[1]
const operands[0] = 5;
const newSum = operands[0]+operands[1];

output:
newSum : 11
```

# Objects
## Definition
