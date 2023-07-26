# SCOPE & HOISTING QUESTIONS:

[Excercise1](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week3-day2-tasks/tasks.md)

The answer is C : 1, ReferenceError, ReferenceError
- Variables declared with var are function-scoped or globally scoped, not block-scoped. Therefore, the variable a is accessible outside the if block, and its value will be 1.
- Variables declared with let and const are block-scoped, which means they are only accessible within the block they are declared in. So, attempting to access them outside the if block will result in a ReferenceError.

[Excercise2](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week3-day2-tasks/tasks.md)

The answer is A : undefined, ReferenceError

-  var a has function scope or global scope. Since var declarations are hoisted to the top of their scope, the variable a is hoisted, and its declaration is moved to the top of the function. However, the initialization a = 1; is not hoisted, so at the time of the first console.log(a);, the variable a exists but is not yet initialized, resulting in undefined.
-  Variables b and c are declared with let and const, respectively, inside the if block. Both let and const declarations are block-scoped and are not hoisted to the top of their scope. Therefore, at the time of the first console.log(b); and console.log(c);, the variables b and c are not yet declared, leading to ReferenceError.

[Excercise3](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week3-day2-tasks/tasks.md)

The answer is B : undefined, ReferenceError

- The first console.log([a, b, c]); statement will output the values of the variables a, b, and c in the outer scope, which are 36, 100, and 45, respectively.
- Inside the if block, new variables with the same names a, b, and c are declared using let and const within the block. These variables have block scope, meaning they only exist within the block.
- The second console.log([a, b, c]); statement will output the values of the variables a, b, and c inside the if block, which are 1, 2, and 3, respectively.
- After the if block, the outer variables a, b, and c retain their values, and the third console.log([a, b, c]); statement will output the values 36, 100, and 45, respectively.
