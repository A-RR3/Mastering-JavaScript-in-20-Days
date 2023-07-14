 **Table of Contents**
=====================
* [Introduction](#Introduction)
* [Async JavaScript](#Async-JavaScript)
* [Promises](#Promises)
* [Coding Exercises](#Coding-Exercises)

# Introduction
This README file highlights some important notes from the [second course](https://frontendmasters.com/courses/javascript-hard-parts-v2/), with some exercises related to it.

# Async JavaScript
- Asynchronicity : the feature that makes dynamic web applications possible.
- Asynchronous is a non-blocking architecture, so the execution of one task isn't dependent on another.
**JavaScript is**
- Single threaded (one command runs at a time)
- Synchronously executed (each line is run in order the code appears)
  

# Promises

#### Problems
- 99% of developers have no idea how they’re working under the hood
- Debugging becomes super-hard as a result
- Developers fail technical interviews
#### Benefits
- Cleaner readable style with pseudo-synchronous style code
- Nice error handling process

# [Question1](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day3-tasks/tasks.md) :

```javascript
const task1 = (cb) => setTimeout(() => {
  const message = "Task 1 has executed successfully!";
  cb(message);
}, 3000);

const task2 = (cb) => setTimeout(() => {
  const message = "Task 2 has executed successfully!";
  cb(message);
}, 0);

const task3 = (cb) => setTimeout(() => {
  const message = "Task 3 has executed successfully!";
  cb(message);
}, 1000);

const task4 = (cb) => setTimeout(() => {
  const message = "Task 4 has executed successfully!";
  cb(message);
}, 2000);

const task5 = (cb) => setTimeout(() => {
  const message = "Task 5 has executed successfully!";
  cb(message);
}, 4000);

const asyncTasks = [task1, task2, task3, task4, task5];

const executeInSequenceWithCBs = (tasks, callback) => {
  const results = [];

  const executeTask = (index) => {
    if (index >= tasks.length) {
      callback(results);
      return;
    }

    const task = tasks[index];
    task((message) => {
      results.push(message);
      executeTask(index + 1);
    });
  };

  executeTask(0);
};

// Example usage:
executeInSequenceWithCBs(asyncTasks, (results) => {
  console.log(results);
});

```
# [Question2](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day3-tasks/tasks.md) :

```javascript
const apis = [
  {
    apiName: "products", 
    apiUrl: "https://dummyjson.com/products",
  }, 
  {
    apiName: "users", 
    apiUrl: "https://dummyjson.com/users",
  }, 
  {
    apiName: "posts", 
    apiUrl: "https://dummyjson.com/posts",
  }, 
  {
    apiName: "comments", 
    apiUrl: "https://dummyjson.com/comments",
  }
];

const executeInParallelWithPromises = async (apis) => {
  const results = await Promise.all(
    apis.map(async (api) => {
      try {
        const response = await fetch(api.apiUrl);
        const data = await response.json();
        return {
          apiName: api.apiName,
          apiUrl: api.apiUrl,
          apiData: data
        };
      } catch (error) {
        console.error(`Error fetching data for ${api.apiName}:`, error);
        return {
          apiName: api.apiName,
          apiUrl: api.apiUrl,
          apiData: null
        };
      }
    })
  );
  return results;
};

// Example usage:
executeInParallelWithPromises(apis)
  .then((results) => {
    console.log(results);
  })
  .catch((error) => {
    console.error('Error executing APIs in parallel:', error);
  });
```

# [Question3](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day3-tasks/tasks.md) :

```javascript
const apis = [
  {
    apiName: "products", 
    apiUrl: "https://dummyjson.com/products",
  }, 
  {
    apiName: "users", 
    apiUrl: "https://dummyjson.com/users",
  }, 
  {
    apiName: "posts", 
    apiUrl: "https://dummyjson.com/posts",
  }, 
  {
    apiName: "comments", 
    apiUrl: "https://dummyjson.com/comments",
  }
];

const executeInSequenceWithPromises = (apis) => {
  const results = apis.reduce((promiseChain, api) => {
    return promiseChain.then((prevResults) => {
      return fetch(api.apiUrl)
        .then((response) => response.json())
        .then((data) => {
          const result = {
            apiName: api.apiName,
            apiUrl: api.apiUrl,
            apiData: data
          };
          return [...prevResults, result];
        })
        .catch((error) => {
          console.error(`Error fetching data for ${api.apiName}:`, error);
          const result = {
            apiName: api.apiName,
            apiUrl: api.apiUrl,
            apiData: null
          };
          return [...prevResults, result];
        });
    });
  }, Promise.resolve([]));

  return results;
};

// Example usage:
executeInSequenceWithPromises(apis)
  .then((results) => {
    console.log(results);
  })
  .catch((error) => {
    console.error('Error executing APIs in sequence:', error);
  });
```
