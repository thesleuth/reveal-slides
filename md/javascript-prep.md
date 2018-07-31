# JavaScript

-
-

## Thinking Like A Programmer

Computers are great at *processing*. They are bad at *understanding*.

When you write a program, you must break down every step into simple pieces.

-

## Drawing Square on a white board

1. Find a whiteboard and a dry erase marker.
2. Uncap the dry erase maker.
3. Hold the marker in your hand.
4. Place the marker against the whiteboard.
5. Move your hand 1 foot to the right.
6. Stop.
7. Move your hand 1 foot down...

-
-

## Statements

Each instruction in JavaScript is a statement.

```javascript
console.log('Hello World!');
console.log('Nice to meet you');
console.log('I love donuts');
```

-

## Comments

```javascript
/*
You can make long comments
with multiple lines here
*/

console.log('Hello World!'); // Or make short comments here
```

-

## Variables

Just like 'x' in algebra, a variable is a named container for a value that can change.

-

## Declaring Variables

Two ways to declare a variable: the bad way and the better way

```javascript
// This line of code sets the variable latitude to the number 40.7
let latitude = 40.7;

// This line of code sets the variable inNorthernHemisphere to true
let inNorthernHemisphere = true;

// variable values can be reassigned
latitude = 29.8;
inNorthernHempisphere = false;
```

-

## Constants

A constant is a named container for a value that can't be reassigned.

```javascript
// This line of code sets the variable location to the string New York City
const location = 'New York City';

// const values cannot be reassigned;
location = "Philadelphia"; // creates an error
```

-

## Declaring variables vs assigning value

You can declare variables and assign their value later.

```javascript
let location;

location = "Philadelphia";
```

-
-

## Data Types
``string`` string of characters
```javascript
let userName = 'Jane Lane';
```
``number`` integer or floating point
```javascript
let myAge = 30;
```
``boolean`` true or false
```javascript
let catsAreBest = true;
```
``undefined`` value that hasn't been defined
```javascript
let favoriteThings;
```
``null`` an explicitly empty value
```javascript
let goodPickupLines = null;
```
-

## Data Types

``object`` a set of key value pairs, i.e. properties and property values
```javascript
let car = {
    make: "ford",
    model: "taurus"
}
```

``array`` a collection of data
```javascript
let array = ["donuts", "pizza", "potato chips"];
```

-

## JavaScript is not type safe

Variable types can be reassigned;

```javascript
let numberOfDonuts = 4; // numberOfDonuts is a number
numberOfDonuts = "four"; // numberOfDonuts is now a string
```

Reassigning types can cause unexpected errors. Be careful!

-
-

## Numbers

Numbers in JavaScript can either be integers or floats (decimal numbers).
JavaScript automatically converts integers to floats when necessary.

```javascript
let numberOfDonuts = 12;
let donutRating = 10.2;
```

## Arithmetic Operators
Once we have numbers, we can use them in operations

```javascript
let totalDonutRating = numberOfDonuts * donutRating;
```
-

## Arithmetic Operators
<table>
    <thead>
      <tr>
        <th>Example</th>
        <th>Name</th>
        <th>Result</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><code>-a</code></td>
        <td> Negation</td>
        <td>Opposite of <code>a</code>.</td>
      </tr>
      <tr>
        <td><code>a + b</code></td>
        <td>Addition</td>
        <td>Sum of <code>a</code> and <code>b</code>.</td>
      </tr>
      <tr>
        <td><code>a - b</code></td>
        <td>Subtraction</td>
        <td>Difference of <code>a</code> and <code>b</code>.</td>
      </tr>
      <tr>
        <td><code>a * b</code></td>
        <td>Multiplication</td>
        <td>Product of <code>a</code> and <code>b</code>.</td>
      </tr>
      <tr>
        <td><code>a / b</code></td>
        <td>Division</td>
        <td>Quotient of <code>a</code> and <code>b</code>.</td>
      </tr>
      <tr>
        <td><code>a % b</code></td>
        <td>Modulus</td>
        <td>Remainder of <code>a</code> divided by <code>b</code>.</td>
      </tr>
    </tbody>
 </table>

-
 
 ## The += operator
 
 We can easily add a number to itself using the ``+=`` operator
 ```javascript
 let sum = 0;
 sum = sum + 2;
 console.log(sum) // sum is equal to 2
 ```
 
 ```javascript
 let sum = 0;
 sum += 2;
 console.log(sum) // sum is equal to 2
 ``` 

-
-
 
 ## Strings
 
 Strings are a collection of characters. You can wrap a string in single or double quotes.
 
 ```javascript
 let favoriteDonut = 'chocolate';
 let otherFavoriteDonut = "strawberry sprinkled".
 ```
 
 Because JavaScript uses quotes to begin and end strings, if you want to use quotes in a string, you need to *escape* it.
 
 ```javascript
 let sentence = 'Dominique\'s donut shop is the best donut shop.'
 ```
-
 
 ## Adding Strings
 
 We can *concatenate* strings using the ``+`` operator.
 ```javascript
 let firstName = "Dominique";
 let lastName = "Clarke";
 let fullName = firstName + " " + lastName;
 ```
 
 You can also use the ``+=`` operator
 
 ```javascript
 let fullName = "";
 fullName += "Dominique"
 fullName += " ";
 fullName += "Clarke"
 ```

-
 
 ## Combining Strings and Numbers
 
 When concatenating strings and numbers, numbers are automatically converted to strings.
 
 ```javascript
 let numberOfDonuts = 2;
 let typeOfDonuts = "chocolate";
 let stock = "We have " + numberOfDonuts + " " + typeOfDonuts + " " + "donuts.";
 ```

-
-

## Objects 

Objects let us store a set of properties, also known as key value pairs

```javascript
let object = {
    property: propertyValue,
    property2: propertyValue2,
}
```

```javascript
let user = {
    username: "donutLover5000",
    birthday: {month: "april", day: 5}
}
```

-

## Accessing Object Properties

You can use dot notation to access object properties

```javascript
console.log(user.username) // outputs donutLover5000
```

Or you can use bracket notation and pass in a string representing the property
```javascript
console.log(user['username']) // outputs donutLover5000
```
-

## Changing Objects

You can use dot or bracket notation to change property values

```javascript
user.username = "pooBear";
user['username'] = "pooBear";
```

-
-

## Functions

**Good programmers are lazy programmers.**

Print out all the numbers between 1 and 10.
```javascript
console.log(1)
console.log(2)
console.log(3)
console.log(4)
console.log(5)
console.log(6)
console.log(7)
console.log(8)
console.log(9)
console.log(10)
```

-

## Do not repeat yourself

```javascript
// prints the numbers between 1 and 10
function print10() {
    for(let i < 1; i <= 10; i++) {
        console.log(i);
    }
}
```
-

## Create generalized, reusable code

Print all the numbers between 1 and n
```javascript
// prints all the numbers between 1 and n
function printN(n) {
    for(let i < 1; i <= n; i++) {
}
```
-

## Anatomy of a function

To declare (create) a function, you can give it a name, then 
include all the code for the function inside curly brackets 

```javascript

// function keyword - function name - parameters
function printN(n) {
    // code block
}
```

-

## Parameters

Parameters, also called arguments, are named containers for a value that will be passed in.

```javascript
// firstNum and secondNum act as aliases for concrete values passed in later
function add(firstNum, secondNum) {
    console.log(firstNum + secondNum);
}

add(2, 2) // prints 4;
```
We can use, or call, the function by its name, passing in required parameters in parenthesis.

-

## Parameter Values

Parameters are assigned values based on the order they are passed into the function.

```javascript
function subtract(firstNum, secondNum) {
    console.log(secondNum - firstNum);
    console.log(firstNum - secondNum);
}

subtract(4, 2) // Prints 2, then -2
```
-

## Parameters are not type specific

```javascript
function add(firstNum, secondNum) {
    console.log(firstNum + secondNum);
}

function subtract(firstNum, secondNum) {
    console.log(secondNum - firstNum);
    console.log(firstNum - secondNum);
}

add("pizza", "donuts");
subtract("pizza", "donuts");
```
-

## Parameters are not type specific

We expected to use numbers in our function, but instead we were passed strings.

Now what?

```javascript
add("pizza", "donuts"); // prints pizzadonuts
subtract("pizza", "donuts"); //prints NaN
```
-

## Parameters are not type specific

```javascript
add("pizza", "donuts"); // prints pizzadonuts
subtract("pizza", "donuts"); //prints NaN
```

JavaScript uses the ``+`` operator to concat strings, so it 
knows what to do when it sees two strings being added together.

Unfortunately, JavaScript doesn't know how to subtract two strings,
so it prints out NaN (Not a Number) when attempting to subtract strings.

Neither of these behaviors were our intention. Be careful with your types!

-

## Parameters of Varying Type

```javascript
function calc(firstNum, secondNum, operation) {
    if(operation === "add") {
        console.log(firstNum + secondNum);
    }
    
    if(operation === "subtract") {
        console.log(firstNum - secondNum);
    }
}

calc(2, 4, "add"); // prints 6

// be careful with order
calc("add", 2, 4): // not what we want
```

-

## Literal vs Variable Parameters

We can pass in literal values (values not attached to a variable reference) 
into a function, or values stored in a variable or constant;

```javascript
const operation = "add";
let firstNum = 2;

calc(firstNum, 4, operation);
```

-

## The Return Keyword

We can pass back the results of our function and use that as a value.

Instead of printing out our results of adding two numbers, let's ``return``
the value so we can use it

```javascript
function add(firstNum, secondNum) {
    return firstNum + secondNum;
}
```

-

## The Return Keyword

When we return a value, we can use it in operations, or store it to a variable (or constant).

```javascript
let sum = add(4, 2);
```

```javascript
let sum = add(4, 2) + 9;
```

```javascript
let sum = add(4, 2) + add(3, 6);
```
-

## The Return Keyword

No matter where return appears in the function, return always 
exits out of the function. Nothing beyond a return will be executed.

```javascript
function add(4, 2) {
    // exits out of the function
    return true;
    // nothing below this line is excuted
    
    console.log(4, 2) // statement is never reached.
}
```

Once the function has its ``return`` value, there's no longer a need
for it to continue further. 

-
-

# Control Flow

-

## The If Statement

Use ``if`` statements to decide which lines of code to execute, based on a condition.

```javascript
if(condition) {
    // statements to excute
}
```

```javascript
let age = 30;

if (age > 18) {
  console.log('You are an adult');
}
```

JavaScript evaluates conditions to a ``boolean``, ``true`` or ``false``.

-

## Comparison Operators

<table>
    <thead>
      <tr>
        <th>Example</th>
        <th>Name</th>
        <th>Result</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><code>a == b</code></td>
        <td>Equal</td>
        <td><strong><code>TRUE</code></strong> if <code>a</code> is equal to <code>b</code> (can be different types).</td>
      </tr>
      <tr>
        <td><code>a === b</code></td>
        <td>Identical</td>
        <td>
      <strong><code>TRUE</code></strong> if <code>a</code> is equal to <code>b</code>, and the same type. </td>
      </tr>
      <tr>
        <td><code>a != b</code></td>
        <td>Not equal</td>
        <td><strong><code>TRUE</code></strong> if <code>a</code> is not equal to <code>b</code> (can be different types).</td>
      </tr>
      <tr>
        <td><code>a !== b</code></td>
        <td>Not identical</td>
        <td><strong><code>TRUE</code></strong> if <code>a</code> is not equal to <code>b</code>, or they are not the same type.</td>
      </tr>
    </tbody>
  </table>

-

## Comparison Operators

<table class="smalltext">
    <thead>
      <tr>
        <th>Example</th>
        <th>Name</th>
        <th>Result</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><code>a &lt; b</code></td>
        <td>Less than</td>
        <td><strong><code>TRUE</code></strong> if <code>a</code> is strictly less than <code>b</code>.</td>
      </tr>
      <tr>
        <td><code>a &gt; b</code></td>
        <td>Greater than</td>
        <td><strong><code>TRUE</code></strong> if <code>a</code> is strictly greater than <code>b</code>.</td>
      </tr>
      <tr>
        <td><code>a &lt;= b</code></td>
        <td>Less than or equal to </td>
        <td><strong><code>TRUE</code></strong> if <code>a</code> is less than or equal to <code>b</code>.</td>
      </tr>
      <tr>
        <td><code>a &gt;= b</code></td>
        <td>Greater than or equal to </td>
        <td><strong><code>TRUE</code></strong> if <code>a</code> is greater than or equal to <code>b</code>.</td>
      </tr>
    </tbody>
  </table>
  
-

## Logical operators

<table>
    <thead>
      <tr>
        <th>Example</th>
        <th>Name</th>
        <th>Result</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><code>a &amp;&amp; b</code></td>
        <td>And</td>
        <td><strong><code>TRUE</code></strong> if both <code>a</code> and <code>b</code> are <strong><code>TRUE</code></strong>.</td>
      </tr>
      <tr>
        <td><code>a || b</code></td>
        <td>Or</td>
        <td><strong><code>TRUE</code></strong> if either <code>a</code> or <code>b</code> is <strong><code>TRUE</code></strong>.</td>
      </tr>
      <tr>
        <td><code>!a</code></td>
        <td>Not</td>
        <td><strong><code>TRUE</code></strong> if <code>a</code> is not <strong><code>TRUE</code></strong>.</td>
      </tr>
    </tbody>
  </table>

-

## Truthy and Falsy

```javascript
function logTruthiness(val) {
    if(val) {
        console.log("Truthy!");
    } else {
        console.log("Falsy.");
    }
}
```
-

## Truthy and Falsy

```javascript
// Outputs: "Truthy!"
logTruthiness(true);

// Outputs: "Truthy!"
logTruthiness({});

// Outputs: "Truthy!"
logTruthiness([]);

// Outputs: "Truthy!"
logTruthiness("some string");

// Outputs: "Truthy!"
logTruthiness(3.14);
```

-

## Truthy and Falsy

```javascript
// Outputs: "Falsy."
logTruthiness(false);

// Outputs: "Falsy."
logTruthiness(null);

// Outputs: "Falsy."
logTruthiness(undefined);

// Outputs: "Falsy."
logTruthiness(NaN);

// Outputs: "Falsy."
logTruthiness(0);

// Outputs: "Falsy."
logTruthiness("");
```

-

## The if else statement

If you have multiple conditions, you can use ``else if``.

```javascript
let age = 30;

if (age >= 35) {
  console.log('You can vote AND run for President!'); // win not run
} else if (age >= 30) {
  console.log('You can vote AND run for the Senate!'); // will run
} else if (age >= 18) {
  console.log('You can vote!'); // will not run
} else {
  console.log('You can\'t vote, but you can write your representatives.'); // will run
}
```

Only one condition will be met.

-

## Combining Individual If Statements

```javascript
let age = 30;

// individual if statement
if (age >= 35) {
  console.log('You can vote AND run for President!'); // will run
}

if (age >= 30) {
  console.log('You can vote AND run for the Senate!'); // win run
} 

if (age >= 18) {
  console.log('You can vote!'); // will run
} else {
  console.log('You can\'t vote, but you can write your representatives.'); // will not run
}
```
-

## Combining Conditionals

You can use logical operators to combine conditions

```javascript
let age = 30;
let yearsAsCitizen = 30;

// If you are over 30 and you've been a citizen for over 9 years
if (age >=30 && yearsAsCitizen > 9) {
  console.log('You can run for the Senate!');
} else {
  console.log('You are not eligible to run for the Senate');
}
```

```javascript
let birthYear = 1992;

// If you were born before 1980 or born after 2000
if(birthYear < 1980 || birthYear > 2000) {
    console.log('You are not a millennial');
}
```

-
## The Switch Statement

The ``switch`` expression is evaluated once. The value of the expression is compared with the 
values of each case. If there is a match, the associated block of code is executed.

```javascript
let numericalDay = 1;

switch (numericalDay) {
    case 0:
        day = "Sunday";
        break;
    case 1:
        day = "Monday";
        break;
    case 2:
        day = "Tuesday";
        break;
    case 3:
        day = "Wednesday";
        break;
    case 4:
        day = "Thursday";
        break;
    case 5:
        day = "Friday";
        break;
    case 6:
        day = "Saturday";

```
-

## The Switch Statement

* If multiple cases matches a case value, the first case is selected.

* If no matching cases are found, the program continues to the default label.

* If no default label is found, the program continues to the statement(s) after the switch.

* Switch cases use strict comparison (===).
  
* The values must be of the same type to match.

-

## The Break Keyword

* When JavaScript reaches a ``break`` keyword, it breaks out of the switch block.

* This will stop the execution of more code and case testing inside the block.

* When a match is found, and the job is done, it's time for a ``break``. There is no need for more testing.
A ``break`` can save a lot of execution time because it "ignores" the execution of all the rest of the code in the switch block.

* It is not necessary to break the last case in a switch block. The block breaks (ends) there anyway.

-

## The Default Keyword

If today is neither Saturday (6) nor Sunday (0), write a default message.

```javascript
let numericalDay = 1;

switch (numericalDay) {
    case 6:
        text = "Today is Saturday";
        break; 
    case 0:
        text = "Today is Sunday";
        break; 
    default: 
        text = "Looking forward to the Weekend";
}
```

-

## Common Cases

Sometimes you will want different switch cases to use the same code.

```javascript
let numericalDay = 1;

switch (numericalDay) {
    case 4:
    case 5:
        text = "Soon it is Weekend";
        break; 
    case 0:
    case 6:
        text = "It is Weekend";
        break;
    default: 
        text = "Looking forward to the Weekend";
}
```



