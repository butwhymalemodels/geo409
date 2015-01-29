#Module 05: JavaScript Array Data Structures and Control Structures

##Overview

This lab does the following:

* introduces you to the array data structure, including:
    * array construction
    * accessing array values
    * adding elements to arrays
* looping in JS programming
    * for loops
    * while loops
* conditional logic in JS programming (if/else statements)

##Readings and additional resources

* Read the sections on Arrays in Chapter 4 of Haverbeke (2014) [Data Structures: Objects and Arrays](http://eloquentjavascript.net/04_data.html)
* Read the sections on "Control Flow" in Chapter 2 of Haverbeke (2014) [Program Structure](http://eloquentjavascript.net/02_program_structure.html)
* Read more about [JavaScript Arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) in the Mozilla Developer's Network
* Read more about [for loops](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for), [while loops](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/while), and [if/else statements](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else)

## The Array data structures

In module 4 we learned how to assign values to variables, to store for later use in the program. While individual variables are useful, often we wish to store larger amounts of values together. In computer programming, use **data structures** to organize data in predictable ways so the computer can efficiently work with these data. We'll be using two data strcutures in this course: arrays (the current module) and objects (module 07). 

An array is a special data type (remember some other types from the previous module: Strings, Numbers, Booleans) that organizes other values as an ordered list. The array itself can then assigned to a variable, in the same way we assign other values to variables. 

###Constructing an Array literal

Arrays are most commonly constructed using what's known as an **array literal**, that is, we *literally* define the array's values using square brackets `[]`. We can create an empty array and assign it to the a variable with the following JavaScript code:

```javascript
    var cities = []; // creates an empty array
    console.log(cities);
```

We can also construct an array with values as the list items:

```javascript
    var cities = ["Frankfurt", "Louisville", "Lexington"];
    console.log(cities);
```

The previous code created an array named `cities` that consists of three String values (the names of the three cities).

Arrays accept any values within it as list items. So, for instance, instead of constructing an array of String values, we could build one with Numbers:

```javascript
    var populations = [25527, 756832, 308428];
    console.log(populations);
```

The values within an array don't need to all be the same type, however. So we could build an array of various data types:

```javascript
    var populations = ["Frankfurt", 756832, false];
    console.log(populations);
```

Arrays can even contain other arrays! In this way, we can create what's known as a "multidimensional array," which can start to look fairly complicated:

```javascript
    var twoDArray = [
        ["Frankfurt", "Louisville", "Lexington"],
        [25527, 756832, 308428],
        ["Frankfurt", 756832, false]
    ];
    console.log(twoDArray);
```

###Accessing Array values

How do we access the individual values within an array? As we said above, arrays are an ordered list. This order is important, because each item in the array has an index value (i.e., its place within the array). We access individual index values using the name of the array and square values, e.g., `arrayName[indexNumber]`.

**But here's the tricky part, so pay attention to this!** The first index of an array is always zero, not one! So, to access the first item within an array, we'd use the following syntax:

```javascript
    var cities = ["Frankfurt", "Louisville", "Lexington"];
    console.log(cities[0]); // outputs the String "Frankfort"
```

Logically then, we can access the other values using their respective index values. However, if we attempt to use an index value that doesn't exist, Javascript doesn't find a value and therefore will output another data type of *undefined*. JavaScript is quite flexible in this way, it is nice that it doesn't throw an error in this case!

```javascript
    var cities = ["Frankfurt", "Louisville", "Lexington"];
    console.log(cities[0]); // outputs the String "Frankfort"
    console.log(cities[1]); // outputs the String "Louisville"
    console.log(cities[2]); // outputs the String "Lexington"
    console.log(cities[3]); // outputs undefined
```

Note that we can also access an array value and assign that value to an additional variable:

```javascript
    var cities = ["Frankfurt", "Louisville", "Lexington"];
    var city = cities[0];
    console.log(city);
```

What about that 2-dimensional array that we looked at above? How do we access values within those nested arrays? For this, we use a double bracket syntax, i.e., `arrayName[indexValue][indexValue]`. For example:

```javascript
    var twoDArray = [
        ["Frankfurt", "Louisville", "Lexington"],
        [25527, 756832, 308428],
        ["Frankfurt", 756832, false]
    ];
    console.log(twoDArray[0][2]); // output will be Lexington
    console.log(twoDArray[2][1]); // output will be 756832

###Updating and adding values to an array

Now that we know how to make an array, and access its values, let's work on updating values within an array, and adding new values to it. Let's say we've created an array of Numberic values representing years:

```javascript
    var years = [2010, 2011, 2022, 2013, 2014];
    console.log(years);
```

We notice that we've entered the wrong value for the third elemnt in that array. Sure, we could just fix it right in the array definition, in this example. But let's pretend we want to update the array programmatically (we'll actually need to do this in more complex and dynamic programs). To do so, we use the same syntax as when accessing an element of an array through its index (square brackets), but now we use the assignment operator to give that index  a new value:

```javascript
    var years = [2010, 2011, 2022, 2013, 2014];
    console.log(years);
    years[2] = 2012;
    console.log(years); // we can see that the array has been updated!
```

Okay, what about adding additional values to our array? We can do this in the same way as we update our array with the square brackets and assignment operator. For example:

```javascript
    var counties = [];
    console.log(counties);
    counties[0] = "Adair";
    console.log(counties); // output is a single item array ["Adair"]
    counties[1] = "Allen";
    console.log(counties); // output is now ["Adair", "Allen"]  
```

What happens if we create a value at an index value beyond the current length of the array? Try it and see!

```javascript
    counties[5] = "Anderson";
    console.log(counties); // what is this output?  
```

The array has been constructed to now hold 4 items (remember the first index is zero!), and the undefined values have been given index values.

We want to introduce a new key term at this point, that of JavaScript **properties**. We'll be getting more into properties when we discuss methods in module 06 and objects in module 07, but for now we can think of properties as similar to a variable (i.e., stores/retrieves a value or bit of information) that is attached to another object, such as an array. Properties are attached to arrays (and other objects) using a period, a convention known as "dot notation" or "dot syntax." We're only going to talk about one array property now, that of `length`, or the number of values held by an array. If we want to know the number of values in an Array, we can access that value with `arrayName.length`.

```javascript
    var cities = ["Frankfurt", "Louisville", "Lexington"];
    console.log(cities.length);
    var years = [2010, 2011, 2022, 2013, 2014];
    var yearsNum = years.length;
    console.log(yearsNum);
```

We'll be using the *length* property in the looping mechanisms below.

##Looping in JS programming

So far, when we've loaded our web browser (or hit Refresh), our JavaScript has executed from the top of the script to the bottom. This is to say, the "flow of program execution" of the program has moved in one direction, from top to bottom. However, often we want to interrupt this flow of execution in various ways. This is where the idea of **control structures** come into play. Looping is a common way of interrupting the flow of execution.

The *for loop* is the most common (and computationally fastest) of the looping mechanisms. The syntax of the for loop may look confusing at first, but it is common and you'll be using it frequently, so study it carefully, as well as the output in the JavaScript Console:

```javascript
console.log("before the for loop");
for (var i = 0; i < 5; i++) {
  console.log(i); // outputs numbers from 0 to 4
}
console.log("after the for loop");
```

The `for` statement (a reserved keyword in JavaScript) is always followed by the parentheses. Within the parentheses we see we've declared a variable named `i` (which generally stands for *integer*) and assigned a value of zero to it. This expression initializes, or begins, a counter variable. After the semicolon is an expression which checks to see if the value of i is less than 5 (in this case). If that expression resolves itself to true, then the expression following the third semicolon is executed. If not, the looping mechanism stops. Following the third semicolon within the parentheses is a statement using an operator we haven't seen yet, the double plus sign. This operator is equivalent to `i = i + 1`. This third expression within the parentheses therefore acts to incremement the counter variable.

The loop will continue to execute the statements contained within the curly brackets (what's known as a *block statement*) until the expression contained within the parentheses resolves to false. Then, the program will continue the normal flow of execution below the for loop.

We often use for loops in JavaScript through looping through values of an array. To do this, we'll use the length of the array in the expression that determines how long the loop should continue. Study this code and it's output carefully. Think about the flow of execution as the loop progresses through incrementing the value of i, and how the variable i is used to access the index values of the array. This is a classic for loop in computer science, and one you'll get to know well:

```javascript
    var cities = ["Frankfurt", "Louisville", "Lexington"];
    for (var i = 0; i < cities.length + 1; i++) {
        console.log(i); // output the current value of i
        console.log(cities[i]); // use i to access an index of the Array
    }
```

Think carefully about why we've added 1 to the cities.length value. Why would we do this? Remove the `+ 1` and consider the resultant output. Hint: it relates to the zero-index.

Alternatively, we could use a for loop to construct an array of integers from 1 to 10.

```javascript
    var newArray = []; // define an empty array
    for(var i = 0; i < 10; i++) {
        newArray[i] = i + 1;
    }
    console.log(newArray); // output will be [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

Isn't that just a kick in the pants!?

An alternative to the classic for loop in JavaScript is a while loop. This loop works in a similar way as the for loop, though the syntax is different. There is only one expression within the parentheses, and as long as it resolves to `true`, then the loop will continue. Note that we declare and assign the variable of i externallly to the looping structure itself, while i is incremented within the block statement itself: 

```javascript
var cities = ["Frankfurt", "Louisville", "Lexington"];
var i = 0;
while (i < cities.length){  
    console.log(i);
    console.log(cities[i]);
    i++		
}
```

This while loop in this example operates exactly like for loop above. Generally speaking, you'll use a for loop when you know how many times you want to loop, such as for the number of elements in a dataset. You'll use a while loop when the value used in the expression is unknown (which, may not make sense given these simple examples, but will become clearer in more complex programs).

## Control structures: the if and else statements

The for and while statements introduced above allow us to disrupt the  normal flow of a programs execution. If and else statements allow for even further control over the flow of the program and play very nicely with looping.

Before we interject them within a loop, let's look at these statements in a basic sense. The syntax is similar to that of the loops. First the statement `for`, followed by parentheses that contain an expression that evaluates to either true or false, followed by block statements contained within curly braces (Note that JavaScript is a very flexible language, and you may see examples of loops that do not use the curly braces. It is, however, good practice to use them and is recommended within this course). Test the following code:

```javascript
var iguanaEyes = 2;
if(iguanaEyes == 2) {
   console.log('the Iguana has two dreamy eyes');
}
```

Because the number 2 is equivalent with the value of iguanaEyes, the expression evaluates to true and the *console.log* statement within the braces is executed. Try changing the value of `iguanaEyes` to 1 and running the code again.

```javascript
var iguanaEyes = 1;
if(iguanaEyes == 2) {
   console.log('The Iguana has two dreamy eyes.');
}
```

There is no output! The program has run successfully. The conditional expression evaluated to false, and therefore the statements within the curly braces did not execute. However, it'd be nice if we knew this. Let's include another statement, the *else* statement then. Else statements just follow an *if* statement.

```javascript
var iguanaEyes = 1;
if(iguanaEyes == 2) {
   console.log('The Iguana has two dreamy eyes.');
} else {
   console.log('The Iguana has some number other than two of dreamy eyes.');
}
```

In this case, the conditional statement evaluates to false and the code within the else block statement runs. How can we get even more control over how the code evaluates the case of this visually-impared iguana? We can add subsequent *else if* statements before a final *else* statement. The comments within this example help explain how the if, else if, and else statements  work.

```javascript
var iguanaEyes = 1;
if(iguanaEyes == 2) { // if this condition is met
   console.log('The Iguana has two dreamy eyes.'); // this statement is executed
} else if(iguanaEyes == 1) { // otherwise if this condition is met
   console.log('oh no! The Iguana has lost a dreamy eye.'); // this statement is executed
} else { // finally, if the previous conditions have not been met, this block statement runs
   console.log('The Iguana has some number other than two or one dreamy eyes.');
}
```

*If* and *else* statements are useful by themselves. But they're also incredibly powerful when using inside looping mechanisms. Let's consider the following code. Pretend we have an array of city names, and we have the name of a particular city stored as a variable. We want a piece of code to test whether that city name is contained with the Array. We can use a loop and an *if* statement to perform this test:

```javascript
var cities = ["Frankfurt", "Louisville", "Lexington"];
var testCity = "Louisville";
for (var i = 0; i <= cities.length; i++) {
    if(cities[i] == testCity) {
        console.log(testCity + " is found in the city Array!");
    }
}
```

Furthermore, we could use the loop to tell us where in the Array that city is found:

```javascript
var cities = ["Frankfurt", "Louisville", "Lexington"];
var testCity = "Louisville";
for (var i = 0; i <= cities.length; i++) {
    if(cities[i] == testCity) {
        console.log(testCity + " is found in the city Array at index "+ i+"!");
    }
}
```

To follow from the previous simple examples, we can include an else statement to let us know that the value hasn't been found within the Array:

```javascript
var cities = ["Frankfurt", "Louisville", "Lexington"];
var testCity = "Bowling Green";
for (var i = 0; i <= cities.length; i++) {
    if(cities[i] == testCity) {
        console.log(testCity + " is found in the city Array at index "+ i+"!");
    } else {
        console.log(testCity + " was not found within the Array at index "+ i+"!");
    }
}
```

Often when we loop, we're looking for a conditional statement to evaluate to true (e.g., we're looking for a match), but we no longer need the loop to continue once that condition has been met. In this case we'll use a special statement known as a *break* statement to "break" out of the loop, thereby returning the flow of execution of the script to its normal course. Examine the following example, which will log to the Console the values within the Array until it finds one that matches the number 2012:

```javascript
var years = [2008, 2009, 2010, 2011, 2012, 2013, 2014, 2015];
for(var i = 0; i <= years.length; i++) {
  if(years[i] == 2012) {
    break;
  } else {
    console.log(years[i]);
  }
}
```

##Summary

Now that you've learned how to use JavaScript variables, values, operators, and statements within a data structure as an Array, and you can control the flow of the program's execution, you can actually do a lot of programming! Bla bla bla Iguana says look into my eyes. Easter egg to see if Zook's gotten this far. :)

###Glossary

* **data structure**: a data type in JavaScript (or other programming language) used to store and manipuate multiple values of a data set
* **array**: a data structure that orders values as a list with specific index values
* **bracket syntax**: the use of square brackets to access and assign values to specific index positions within an array (or object ... addressed in Module 07)
* **property**: when used with an array, stores information about that array, such as its length
* **dot notation or dot syntax**: the use of a period to concatenate a property or method to an object 
* **control structure**: the use of looping mechanisms and conditional statements (e.g., if/else) to control the flow of a programs execution
* **for loop**: a looping structure that iterates a counter variable until a given expression is no longer resolve as true
* **while loop**: a looping structure that continues until a given expression is evaluated as false
* **if statement**: executes a statement (or block statement) if a specificed condition is true
* **else statement**: executes a statement (or block statement) if a previous if condition does not evaluate to true
* **break statement**: a statement that breaks the flow of a program's execution from the  looping structure and returns to the normal flow

