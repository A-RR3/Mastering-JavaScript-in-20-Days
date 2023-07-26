# ADVANCED SCOPE
[Question1](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week3-day4-tasks/tasks.md)

The reason for the unexpected output is due to the closure behavior of JavaScript and how the setTimeout function works. The setTimeout function is asynchronous, and it creates a closure over the i variable, but it does not capture the value of i at the time the setTimeout function is called. Instead, it captures the reference to the i variable.
As a result, when the setTimeout callbacks are executed after the loop has finished running, they all refer to the same variable i, which has the final value of 5.
To fix this issue and achieve the desired output, we need to create a new scope for each iteration of the loop so that each setTimeout callback captures the correct value of i. One way to achieve this is by using an IIFE (Immediately Invoked Function Expression) inside the loop. The IIFE will create a new scope and capture the current value of i for each iteration.
Here's the updated code to fix the issue:

```javascript
for (var i = 0; i < 5; i++) {
  (function (index) {
    setTimeout(function () {
      console.log("value of [i] is: ", index);
    }, 100);
  })(i);
}
```
Explanation:

- We wrap the setTimeout function inside an IIFE (function(index) { ... })(i).
- The IIFE is immediately invoked with the current value of i as an argument. This creates a new scope for each iteration of the loop, and the argument index will capture the correct value of i for that iteration.
- Inside the IIFE, we use the index variable instead of i for the console.log statement inside the setTimeout callback. This ensures that each callback prints the correct value of i.
- With this fix, the output will be:  "value of [i] is: ", 0 "value of [i] is: ", 1 "value of [i] is: ", 2 "value of [i] is: ", 3 "value of [i] is: ", 4


[Question2](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week3-day4-tasks/tasks.md)
To achieve the desired output, the array should be created outside the loop so that it persists across iterations and accumulates the values of i. Here's the fixed code:
```javascript
let array = [];

for (let i = 0; i < 5; i++) {
   array.push(i);
}

console.log("Current array is: ", array);

```
