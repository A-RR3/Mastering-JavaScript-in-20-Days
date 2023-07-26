# Scope & Function Expressions

#### [Question1 link](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week3-day3-tasks/tasks.md)

```javascript
const arrowHOF = (normalFunc) => {
  return (...args1) => {
    return (...args2) => {
      const result = normalFunc(...args1);
      for (let i = 0; i < args2[0]; i++) {
        console.log(result);
      }
    };
  };
};

```
In this implementation, the arrowHOF function returns a new arrow function that takes args1 as its input and returns another arrow function. The second arrow function takes args2 as its input, calculates the result by calling the original normalFunc with args1, and then logs the result args2[0] number of times in the console. The ...args1 and ...args2 are the rest parameters that allow us to accept multiple arguments as arrays.

#### [Question2 link](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week3-day3-tasks/tasks.md)

```javascript
// Example object
const obj = {
  name: 'John',
  greet: function (greeting) {
    console.log(`${greeting}, ${this.name}!`);
  }
};

const preserveThis = (func) => {
  return func.bind(func);
};

// Wrap the greet function using preserveThis
const preservedGreet = preserveThis(obj.greet);

// Call the wrapped function as a method of the object
preservedGreet('Hello'); // Output: "Hello, John!"

```

To preserve the original this context when calling a method of an object, you can use the bind() method of the input function. The bind() method creates a new function that, when called, has its this keyword set to the provided value.

Let's implement the preserveThis function:

javascript
Copy code
const preserveThis = (func) => {
  return func.bind(func);
};
- In this implementation, func.bind(func) is used to bind the this context of the input function func to itself. It creates a new function with the same behavior but with the this context preserved.
- When calling preservedGreet('Hello'), the this context is preserved, and the output will be "Hello, John!" as expected.

#### [Question3 ex1 link](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week3-day3-tasks/tasks.md)

-  Functions declared within another function have access to the variables declared in their containing function.
-  In this case, the inner1 function has access to the variable x due to the closure, which allows it to "remember" the environment in which it was created

#### [Question3 ex2 link](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week3-day3-tasks/tasks.md)
- The inner2 function is defined inside the outer2 function and also declares a variable x with the value 20. This creates a new local variable x within the scope of the inner2 function, which shadows the outer x variable. JavaScript uses lexical scoping, so the inner x variable takes precedence within the scope of inner2.
- Since the inner x variable is declared within the scope of the inner2 function and shadows the outer x variable, the console.log(x); statement within inner2 will print 20.
- The outer x variable with the value 10 is not accessible within the inner2 function due to variable shadowing.
