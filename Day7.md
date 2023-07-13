In this README file, I will be solving programming exercises on javascript principles, functions and callbacks related to topics from the course [JavaScript: The Hard Parts, v2](https://frontendmasters.com/courses/javascript-hard-parts-v2/)

### [Use Higher-Order Functions map, filter, or reduce to Solve a Complex Problem](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/use-higher-order-functions-map-filter-or-reduce-to-solve-a-complex-problem)

```javascript
const squareList = (arr) => {
  // Only change code below this line
  return arr
          .filter(num => num > 0 && num % parseInt(num) === 0)
          .map(num => Math.pow(num, 2));
  // Only change code above this line
};

const squaredIntegers = squareList([-3, 4.8, 5, 3, -3.2]);
console.log(squaredIntegers);
```


### [Apply Functional Programming to Convert Strings to URL Slugs](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/apply-functional-programming-to-convert-strings-to-url-slugs)

```javascript
// the global variable
var globalTitle = "Winter Is Coming";

// Add your code below this line
function urlSlug(title) {
  return title
    .toLowerCase()
    .trim()
    .split(/\s+/)
    .join("-");
}
// Add your code above this line

var winterComing = urlSlug(globalTitle); // Should be "winter-is-coming"
```


### [Question 1: Functions and Callbacks](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day1-tasks/tasks.md)

```javascript
function mapAsync(array, callback) {
  return new Promise((resolve, reject) => {
    const mappedArray = [];

    function processElement(index) {
      if (index >= array.length) {
        resolve(mappedArray); 
        return;
      }

      Promise.resolve(callback(array[index]))
        .then(mappedValue => {
          mappedArray[index] = mappedValue;
          processElement(index + 1); // Process the next element
        })
        .catch(reject); // Reject the Promise if an error occurs
    }

    processElement(0);
  });
}

```

### [Question 2: Call Stack and Recursion](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day1-tasks/tasks.md)

```javascript
function sumRange(start, end) {
  //if the start and end values are the same, return the value itself
  if (start === end) {
    return start;
  }

  // calculate the sum of the current start value and the sum of the range from start+1 to end
  return start + sumRange(start + 1, end);
}

```
