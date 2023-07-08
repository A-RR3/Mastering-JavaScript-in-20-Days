
  **Table of Contents**
=====================
* [Introduction](#Introduction)
* [Event & Handlers](#Event-&-Handlers)
* [Conditionals](#Conditionals)
* [Map & Filter](#Map-&-Filter)
* [Doggos Quiz Game](#Doggos-Quiz-Game)
* [Coding Exercises](#Coding-Exercises)

# Introduction
This README file highlights some important notes from the [first course](https://frontendmasters.com/courses/javascript-first-steps/) on topics listed below.


# Event & Handlers

// TODO 6A: Use a for loop to add a click event listener to each of the optionButtons
// TODO 6B: Within the event handler function, display the fact's explanation by setting the text of the explanation element


// TODO 7: Within the event handler function, 
// Use a for loop to disable all the option buttons


// TODO 8: Within the event handler function,
// Get the guessed value from the clicked button
// Use a conditional to compare the guess to the fact's answer
// and add the "correct"/"incorrect" class as appropriate


# Conditionals

# Map & Filter

# Doggos Quiz Game

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

  
  
