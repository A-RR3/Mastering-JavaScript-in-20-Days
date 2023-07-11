**Table of Contents**
=====================
* [Introduction](#Introduction)
* [Data Fetching & Promises](#Data-Fetching-&-Promises)
* [Destructuring Data](#Destructuring-Data)
* [Async](#Async)
* [Modules](#Modules)


# Introduction
This README file highlights some important notes from the [first course](https://frontendmasters.com/courses/javascript-first-steps/), besides some exercises on the topics included.

# Data Fetching & Promises
- API's provide URL's that point at data we want to use
- It takes a while to fetch data from the internet, thats why the fetch function returns a promise
- Promises can be in three states: pending, fulfilled, rejected\
- Promises are asynchronous

# Destructuring Data
- Declaring multiple variables at once
- Extracting variables from an object an make them variables in our scope
#### Destructuring Example
In the example below, the firstName and lastName properties are assigned to the fName and lName variables respectively.
```javascript
let person = {
    firstName: 'John',
    lastName: 'Doe'
};
let { firstName: fname, lastName: lname } = person;
```

# Async
- Each time when an async function is called, it returns a new Promise
- Async functions can contain zero or more await expressions.

```javascript
const files = { x: 10, z: 50 };

const readVal = (vName) => {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            if (files[vName]) {
                const v = files[vName];
                resolve(v);
            } else {
                reject("value not found");
            }
        }, 2000);
    });
};

const main = async() => {
    console.log("hello before");
    try {
        const x = await readVal("x");
        const y = x * 2;
        console.log(y);
    } catch (error) {
        console.log(error);
    } finally {
        console.log("finally always gets executed");
    }

    console.log("hello after");
};

const x = readVal("x");
const z = readVal("z");

Promise.all([x, z]).then((results) => {
    console.log(results);
});
main();
```

# Modules
- Modules are imported from external files with the import statement.
- Break up your code into separate files.
