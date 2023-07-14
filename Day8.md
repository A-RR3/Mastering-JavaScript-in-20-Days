
  **Table of Contents**
=====================
* [Introduction](#Introduction)
* [Functions & Callbacks](#Functions-&-Callbacks)
* [Closure](#Closure)
* [Coding Exercises](#Coding-Exercises)

# Introduction
This README file highlights some important notes from the [second course](https://frontendmasters.com/courses/javascript-hard-parts-v2/), with some exercises related to it.


# Functions & Callbacks

 - Higher order function takes in a function or passes out a function.
 - Solution for the DRY (don't repeat yourself) problem.
 - Callbacks are a core aspect of async JavaScript, and are under-the-hood of promises, async/await


```javascript
function copyArrayAndManipulate(array, instructions) {
    const output = [];
    for (let i = 0; i < array.length; i++) {
        output.push(instructions(array[i]));
    }
    return output;
}

function DevideBy2 = (input) => return input/2 ;
function multiplyBy2(input) { return input * 2; }
const result = copyArrayAndManipulate([1, 2, 3], multiplyBy2);
const result = copyArrayAndManipulate([1, 2, 3], DevideBy2);

```
  
# Closure
Closure gives access to an outer function's scope from an inner function, Here are some important notes from the [course](https://frontendmasters.com/courses/javascript-hard-parts-v2/).

- When our functions get called, we create a live store of data (local memory/variable environment/state) for that function’s execution context.
- All functions data records are stored in a stack.
- When a function finishes execution, its execution record will be deleted except for the returned value.
- When an inner function is defined inside an outer function, it gets a bond to the surrounding Local Memory (“Variable Environment”) in which it has been defined.
- Callbacks and Promises rely on closure to persist state in an asynchronous environment.

# Coding Exercises
### [Question1](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day2-tasks/tasks.md) : Write a closure named createCounter that takes an initial value start and returns a function. The returned function, when invoked, should increment the counter by 1 and return the updated value.

```javascript
function createCounter( start ) {
    let counter = start;

    function incrementCounter() {
        counter++;
    }
    return incrementCounter;
}
const myNewFunction = createCounter(start);
myNewFunction();
myNewFunction();

```
### [Question2](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day2-tasks/tasks.md) : Write a closure named calculateAverage that takes an array of numbers, nums, and returns a function. The returned function, when invoked, should calculate and return the average of the numbers in the array.
  
```javascript
function calculateAverage(nums) {
    let output = 0;
    let count = 0;
    let sum = 0;
    for (let i = 0; i < nums.length; i++) {
        count++;
        sum += nums[i];
    }
    output = sum / count;
    return output;
}

const nums = [1, 2, 3]
console.log(calculateAverage(nums)); //2

```

### [Question3](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day2-tasks/tasks.md): Write a closure named powerOf that takes a base number base and returns a function. The returned function, when invoked with an exponent exp, should calculate and return the result of base raised to the power of exp.

```javascript
function powerOf(base) {
    return function(exp) {
        return Math.pow(base, exp);
    };
}

const powerOfTwo = powerOf(2);
console.log(powerOfTwo(3)); // 8
```

### [Question4](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day2-tasks/tasks.md) :Write a closure named compose that takes multiple functions as arguments and returns a new function. The returned function should apply the provided functions in reverse order, passing the result of each function as an argument to the next function.

```javascript
function compose(...functions) {
    return function(arg) {
        return functions.reduceRight((result, func) => func(result), arg);
    };
}

function addTwo(x) {
    return x + 2;
}

function multiplyByThree(x) {
    return x * 3;
}

function subtractTen(x) {
    return x - 10;
}

const combinedFunc = compose(subtractTen, multiplyByThree, addTwo);
console.log(combinedFunc(5)); // Output: 21
```
