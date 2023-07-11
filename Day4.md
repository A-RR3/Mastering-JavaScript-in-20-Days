
  **Table of Contents**
=====================
* [Introduction](#Introduction)
* [Event & Handlers](#Event-&-Handlers)
* [Conditionals](#Conditionals)
* [Map & Filter](#Map-&-Filter)
* [Project](#Project)
* [Coding Exercises](#Coding-Exercises)

# Introduction
This README file highlights some important notes from the [first course](https://frontendmasters.com/courses/javascript-first-steps/) on topics listed below.


# Event & Handlers
- make a web page interactive
- the web browser fires events when certain things happen in the page (e.g click event)
- detect events using an event listener
- examples of events: click, dbclick, mouseover, mouseout

  
# Conditionals
#### logical and ternary operator
- logical and operator is true only of both values are true
- vertical live operator is true if one value is true
- conditional ternary operator: condition ? valueIfTrue : valueIfFalse
```javascript
let mood ="forecast" === "sunny" ? "happy" : "sad";
//is equivalent to
let mood;
if(mood === "sunny"){
  mood = "happy"
}else{
  mood = "sad"
}
```

# Map & Filter
- methods in JS
- let us process all items in an array
- map gives a resulting array with the result of the function call on each item in the original array
- filter calls true/false function on each item and returns a new array with only the items where the function returns true


# Project
This is the second section of completing the js code inside the script tag at [this link](https://anjana.dev/javascript-first-steps/2-jsquiz-starter.html).
```javascript
   // TODO 1: Declare & assign variables pointing to the corresponding element(s)
    // statement should be the "statement" div
    const statement = document.getElementById("statement");
    // optionButtons should be all the elements within the "options" div
    const optionButtons = document.getElementById("options").children;
    // explanation should be the "explanation" div
    const explanation = document.getElementById("explanation");

    // TODO 2: Declare & assign a variable called fact
    // Its value should be an object with a statement, true/false answer, and explanation
    const fact = {
        statement: "arrays are like objects",
        answer: true,
        explanation: "arrays are kind of object with special properties",
    };

    // TODO 3: Set the text of the statement element to the fact's statement
    statement.textContent = fact.statement;

    // TODO 4: Declare disable & enable functions to set or remove the "disabled" attribute from a given button element
    // disable(button) should set the button element's attribute "disabled" to the value ""
    const disable = (button) => {
        button.setAttribute("disabled", "");
    };
    // enable(button) should remove the attribute "disabled" from the button element
    const enable = (button) => {
        button.removeAttribute("disabled");
    };

    // TODO 5: Declare an isCorrect function that compares a guess to the right answer
    // isCorrect(guess) should return true if the guess matches the fact's answer
    function isCorrect(guess) {
        return guess === fact.answer.toString();
    }

    // TODO 6A: Use a for loop to add a click event listener to each of the optionButtons
    for (let button of optionButtons) {
        button.addEventListener("click", (event) => {
            // TODO 6B: Within the event handler function, display the fact's explanation by setting the text of the explanation element
            explanation.textContent = fact.explanation;

            // TODO 7: Within the event handler function, Use a for loop to disable all the option buttons
            for (let otherButton of optionButtons) {
                disable(otherButton);
            }

            // TODO 8: Within the event handler function,
            // Get the guessed value from the clicked button
            // Use a conditional to compare the guess to the fact's answer
            // and add the "correct"/"incorrect" class as appropriate
            if (isCorrect(button.value)) {
                button.classList.add("correct");
            } else {
                button.classList.add("incorrect");
            }
        });
    }
```
# Coding Exercises

#### Exercise1: [Multiple Conditional Operators](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/use-multiple-conditional-ternary-operators)

```javascript
function checkSign(num) {
  return num > 0 ? "positive"
    : num < 0 ? "negative"
    : "zero";
}
checkSign(10);
```
#### Exercise2: [Golf Code](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/golf-code)

```javascript
const names = ["Hole-in-one!", "Eagle", "Birdie", "Par", "Bogey", "Double Bogey", "Go Home!"];

function golfScore(par, strokes) {
  return strokes === 1
    ? names[0]
    : strokes <= par - 2
    ? names[1]
    : strokes === par - 1
    ? names[2]
    : strokes === par
    ? names[3]
    : strokes === par + 1
    ? names[4]
    : strokes === par + 2
    ? names[5]
    : names[6];
}

golfScore(5, 4);
```
#### Exercise3: [Use the map Method to Extract Data from an Array](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/use-the-map-method-to-extract-data-from-an-array)

```javascript
// Only change code below this line

const ratings = watchList.map(item => ({
  title: item["Title"],
  rating: item["imdbRating"]
}));

// Only change code above this line
```

#### Exercise4: [Use the filter Method to Extract Data from an Array](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/use-the-filter-method-to-extract-data-from-an-array)

```javascript
// Only change code below this line

const filteredList = watchList
  .filter(movie => {
    // return true it will keep the item
    // return false it will reject the item
    return parseFloat(movie.imdbRating) >= 8.0;
  })
  .map(movie => {
    return {
      title: movie.Title,
      rating: movie.imdbRating
    };
  });

// Only change code above this line
```

  
  
