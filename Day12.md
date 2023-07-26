#### [Excercise1](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week3-day1-tasks/tasks.md)
```javascript
function convertStringToNumber(input) {
    if (typeof input === 'string') {
        const result = +input;
        return isNaN(result) ? null : result;
    } else {
        return { value: input, type: typeof input };
    }
}

console.log(convertStringToNumber("42")); // Output: 42 (number)
console.log(convertStringToNumber("3.14")); // Output: 3.14 (number)
console.log(convertStringToNumber("Hello")); // Output: null (not a valid number)
```
#### [Excercise2](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week3-day1-tasks/tasks.md)
```javascript
const checkNaN = (value) => {
  return isNaN(value);
};

console.log(checkNaN(15)); // Output: false
console.log(checkNaN("arwa")); // Output: true
console.log(checkNaN(3.14)); // Output: false
console.log(checkNaN(NaN)); // Output: true
console.log(checkNaN(null)); // Output: false
console.log(checkNaN(undefined)); // Output: true

```

#### [Excercise3](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week3-day1-tasks/tasks.md)
```javascript
function isEmptyValue(value) {
  return value === undefined || value === null || value === '';
}
console.log(isEmptyValue(11)); // Output: false
console.log(isEmptyValue("arwa")); // Output: false
console.log(isEmptyValue(null)); // Output: true
console.log(isEmptyValue(undefined)); // Output: true
console.log(isEmptyValue("")); // Output: true

```

#### [Excercise4](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week3-day1-tasks/tasks.md)
```javascript
function compareObjects(input1, input2) {
    if (typeof input1 !== "object" || typeof input2 !== "object") {
        return [input1, input2];
    }

    const jsonString1 = JSON.stringify(input1);
    const jsonString2 = JSON.stringify(input2);

    return jsonString1 === jsonString2;
}

const obj1 = { name: "arwa", age: 30 };
const obj2 = { name: "arwa", age: 30 };

console.log(compareObjects(obj1, obj2)); // Output: true
console.log(compareObjects(obj1, null)); // Output: false
console.log(compareObjects("Hello", obj1)); // Output: ["Hello", object]
console.log(compareObjects(42, "world")); // Output: [42, "world"]
```
#### [Excercise5](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week3-day1-tasks/tasks.md)
```javascript
const complexCoercion = (input) => {
    if (typeof input === 'number') {
        return (input.toString());
    } else if (typeof input === 'string') {
        return true;
    } else if (input === null || input === undefined) {
        return false;
    } else {
        return input;
    }
};
console.log(complexCoercion(42)); // output: 42 as string
console.log(complexCoercion({ name: "John" })); // Output: { name: "John" } (input is not a primitive type, returns the argument)
```
