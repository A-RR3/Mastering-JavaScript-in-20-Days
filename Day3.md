**Table of Contents**
=====================
* [Introduction](#Introduction)
* [Scoping](#Scoping)
* [Pop Quiz Answers](#Pop-Quiz-Answers)
* [Project](#Project)
* [Coding Exercises](#Coding-Exersices)

# Introduction
This README file highlights some important notes from the [first course](https://frontendmasters.com/courses/javascript-first-steps/), and summarises what I've studied in the "Quiz Project" sections.

# Scoping
- the accessibility of variables to JavaScript.
- The two types of scope are local and global: Global variables are those declared outside of a block. Local variables are those declared inside of a block
- a function scope can access glabal scope and not the reverse
- a global let variable is re-assignable inside the function scope but cost is not.
- variables declared using var are also re-assignable
- var and let are different in how they behave within blocks
#### Example : let vs var
```javascript
//global scope
let name = "arwa";
var gender = "male"
//block scope
{
let name = "sara"
var gender = "female"
}
console.log(name) // arwa
console.log(gender) // female

```

# Pop Quiz Answers
- Strings in JavaScript are immutable, they can't be edited, but we can replace them with new and different strings
- 1+1 === 2 is true sentence
-  '1' + '1' ===2 is false , the plus operator contatinates the strings to '11'
- typeOf['J','F'] === 'array' is false, array is an object because everything in JS is either of type object or primitive (strings,numbers,booleans)

# Project : 
This is the first section of completing the js code inside the script tag at [this link](https://anjana.dev/javascript-first-steps/2-jsquiz-starter.html) .

```javascript
// TODO 1: Declare & assign variables pointing to the corresponding element(s)
    // statement should be the "statement" div
    const statement = document.getElementById("statement");
    // optionButtons should be all the elements within the "options" div
    const optionButtons = document.querySelectors(#Options).children
    // explanation should be the "explanation" div
    const explanation = document.getElementById("explanation")

 // TODO 2: Declare & assign a variable called fact
    // Its value should be an object with a statement, true/false answer, and explanation 
    const fact = [
      statement: "arrays are like objects",
      answer: true,
      explanation: arrays are kind of object with special properties
     };

    
 // TODO 3: Set the text of the statement element to the fact's statement
    statement.textContent = fact.statement;
        

 // TODO 4: Declare disable & enable functions to set or remove the "disabled" attribute from a given button element
    // disable(button) should set the button element's attribute "disabled" to the value ""
   const disable = (button)=>{
     button.setAttribute("disabled","")
    };
    // enable(button) should remove the attribute "disabled" from the button element
    const enable = (button)=>{button.removeAttribute("disabled")}


 // TODO 5: Declare an isCorrect function that compares a guess to the right answer
    // isCorrect(guess) should return true if the guess matches the fact's answer
    function isCorrect (guess) {
    return guess === fact.answer.toString();
    };
    
```

# Coding Exercises

#### Exercise 1: [Return a Value from a Function with Return](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/return-a-value-from-a-function-with-return).

```javascript
function timesFive(num) {
  return num * 5;
}
```

#### Exercise 2: [Global Scope and Functions](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/global-scope-and-functions).

```javascript
const myGlobal = 10;

function fun1() {
  oopsGlobal = 5;
}

// Only change code above this line
function fun2() {
  var output = "";
  if (typeof myGlobal != "undefined") {
    output += "myGlobal: " + myGlobal;
  }
  if (typeof oopsGlobal != "undefined") {
    output += " oopsGlobal: " + oopsGlobal;
  }
  console.log(output);
}
```

#### Exercise 3: [Local Scope and Functions](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/local-scope-and-functions).

```javascript
function myLocalScope() {

  // Only change code below this line
  var myVar;
  console.log('inside myLocalScope', myVar);
}
myLocalScope();

// Run and check the console
// myVar is not defined outside of myLocalScope
console.log('outside myLocalScope', myVar);
```

#### Exercise 4: [Global vs. Local Scope in Functions](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/global-vs--local-scope-in-functions).

```javascript
var outerWear = "T-Shirt";

function myOutfit() {
  var outerWear = "sweater";
  return outerWear;
}

myOutfit();
```


#### Exercise 5: [Stand in Line](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/stand-in-line).

```javascript
function nextInLine(arr, item) {
  // Only change code below this line
  arr.push(item);
  const removed = arr.shift();
  return removed;
  // Only change code above this line
}

// Setup
let testArr = [1, 2, 3, 4, 5];

// Display code
console.log("Before: " + JSON.stringify(testArr));
console.log(nextInLine(testArr, 6));
console.log("After: " + JSON.stringify(testArr));
```
