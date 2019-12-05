# If you can't sleep, just count sheep!!

Task:
Given a non-negative integer, 3 for example, return a string with a murmur: "1 sheep...2 sheep...3 sheep...". Input will always be valid, i.e. no negative integers.

```javascript
var countSheep = function(num) {
  var text = "";
  for (var i = 1; i <= num; i++) {
    text += i + " sheep...";
  }
  return text;
};
```

# Find numbers which are divisible by given number

Complete the function which takes two arguments and returns all numbers which are divisible by given divisor. First argument is an array of numbers and the second is the divisor.

```javascript
function divisibleBy(numbers, divisor) {
  return numbers.filter(n => n % divisor === 0);
}
```

# Century from year

Introduction
The first century spans from the year 1 up to and including the year 100, The second - from the year 101 up to and including the year 200, etc.

Task :
Given a year, return the century it is in.

Input , Output Examples ::
centuryFromYear(1705) returns (18)
centuryFromYear(1900) returns (19)
centuryFromYear(1601) returns (17)
centuryFromYear(2000) returns (20)

```javascript
function century(year) {
  return Math.ceil(year / 100);
}
```

# Are You Playing Banjo?

Create a function which answers the question "Are you playing banjo?".
If your name starts with the letter "R" or lower case "r", you are playing banjo!

The function takes a name as its only argument, and returns one of the following strings:

name + " plays banjo"
name + " does not play banjo"
Names given are always valid strings.

```javascript
function areYouPlayingBanjo(name) {
  return (
    name +
    (name[0].toLowerCase() == "r" ? " plays" : " does not play") +
    " banjo"
  );
}
```

# The 'if' function

Who likes keywords? Nobody likes keywords, so why use them?

You know what keyword I use too much? if! We should make a function called \_if, with its arguments as a logical test and two functions/lambdas where the first function is executed if the boolean is true, and the second if it's false, like an if/else statement, so that we don't have to mess around with those nasty keywords! Even so, It should support truthy/falsy types just like the keyword.

Example:
\_if(true, function(){console.log("True")}, function(){console.log("false")})
// Logs 'True' to the console.

```javascript
function _if(bool, func1, func2) {
  return bool ? func1() : func2();
}
```

# Is n divisible by x and y?

Create a function isDivisible(n, x, y) that checks if a number n is divisible by two numbers x AND y. All inputs are positive, non-zero digits.

Example:
isDivisible(3,1,3)--> true because 3 is divisible by 1 and 3
isDivisible(12,2,6)--> true because 12 is divisible by 2 and 6
isDivisible(100,5,3)--> false because 100 is not divisible by 3
isDivisible(12,7,5)--> false because 12 is neither divisible by 7 nor 5

```javascript
function isDivisible(n, x, y) {
  return n % x == 0 && n % y == 0;
}
```

# Find the first non-consecutive number

Your task is to find the first element of an array that is not consecutive.

E.g. If we have an array [1,2,3,4,6,7,8] then 1 then 2 then 3 then 4 are all consecutive but 6 is not, so that's the first non-consecutive number.

If the whole array is consecutive then return null or Nothing.

The array will always have at least 2 elements1 and all elements will be numbers. The numbers will also all be unique and in ascending order. The numbers could be positive or negative and the first non-consecutive could be either too!

1. Can you write a solution that will return null for both [] and [ x ] though? ( This is not tested, but you can write your own example test. )

```javascript
function firstNonConsecutive(arr) {
  for (let i = 0; i < arr.length - 1; ++i) {
    if (arr[i] + 1 !== arr[i + 1]) {
      return arr[i + 1];
    }
  }
  return null;
}
```

# Messi goals function

Messi is a soccer player with goals in three leagues:

LaLiga
Copa del Rey
Champions
Complete the function to return his total number of goals in all three leagues.

Note: the input will always be valid.

For example:

5, 10, 2 --> 17

```javascript
const goals = (...allLeagueGoals) =>
  allLeagueGoals.reduce((total, goals) => total + goals, 0);
```

# Sum the strings

Create a function that takes 2 positive integers in form of a string as an input, and outputs the sum (also as a string):

sumStr("4", "5") // should output "9"
sumStr("34", "5") // should output "39"

If either input is an empty string, consider it as zero.

```javascript
function sumStr(a, b) {
  return (+a + +b).toString();
}
```
