# Remove duplicate words

Your task is to remove all duplicate words from a string, leaving only single (first) words entries.

Example:

Input:

'alpha beta beta gamma gamma gamma delta alpha beta beta gamma gamma gamma delta'

Output:

'alpha beta gamma delta'

```javascript

#1 Solution :

const removeDuplicateWords = s =>
  s
    .split(" ")
    .filter(function(a, b, c) {
      return b === c.indexOf(a);
    })
    .join(" ");


#2 Solution :

const removeDuplicateWords = s => {
  const set = new Set(s.split(' '));
  return Array.from(set).join(' ');
}


#3 Solution :

const removeDuplicateWords = s => [...new Set(s.split(' '))].join(' ');

```

# Help Bob count letters and digits.

Bob is a lazy man.

He needs you to create a method that can determine how many letters and digits are in a given string.

Example:

"hel2!lo" --> 6

"wicked .. !" --> 6

"!?..A" --> 1

```javascript
const countLettersAndDigits = (input) => input.replace(/[^a-z\d]/gi, "").length;
```

# Currency Conversion

You are currently in the United States of America. The main currency here is known as the United States Dollar (USD). You are planning to travel to another country for vacation, so you make it today's goal to convert your USD (all bills, no cents) into the appropriate currency. This will help you be more prepared for when you arrive in the country you will be vacationing in.

Given an integer (usd) representing the amount of dollars you have and a string (currency) representing the name of the currency used in another country, it is your task to determine the amount of foreign currency you will receive when you exchange your United States Dollars.

However, there is one minor issue to deal with first. The screens and monitors at the Exchange are messed up. Some conversion rates are correctly presented, but other conversion rates are incorrectly presented. For some countries, they are temporarily displaying the standard conversion rate in the form of a number's binary representation!

You make some observations. If a country's currency begins with a vowel, then the conversion rate is unaffected by the technical difficulties. If a country's currency begins with a consonant, then the conversion rate has been tampered with.

Normally, the display would show 1 USD converting to 111 Japanese Yen. Instead, the display is showing 1 USD converts to 1101111 Japanese Yen. You take it upon yourself to sort this out. By doing so, your 250 USD rightfully becomes 27750 Japanese Yen.

function(250, "Japanese Yen") => "You now have 27750 of Japanese Yen."

Normally, the display would show 1 USD converting to 21 Czech Koruna. Instead, the display is showing 1 USD converts to 10101 Czech Koruna. You take it upon yourself to sort this out. By doing so, your 325 USD rightfully becomes 6825 Czech Koruna.

function(325, "Czech Koruna") => "You now have 6825 of Czech Koruna."

Using your understanding of converting currencies in conjunction with the preloaded code shown below, properly convert your dollars into the correct amount of foreign currency.

CONVERSION_RATES = {
"Argentinian Peso": 10,
"Armenian Dram": 478,
"Bangladeshi Taka": 1010010,
"Croatian Kuna": 110,
"Czech Koruna": 10101,
"Dominican Peso": 110000,
"Egyptian Pound": 18,
"Guatemalan Quetzal": 111,
"Haitian Gourde": 1000000,
"Indian Rupee": 63,
"Japanese Yen": 1101111,
"Kenyan Shilling": 1100110,
"Nicaraguan Cordoba": 11111,
"Norwegian Krone": 1000,
"Philippine Piso": 110010,
"Romanian Leu": 100,
"Samoan Tala": 11,
"South Korean Won": 10000100011,
"Thai Baht": 100000,
"Uzbekistani Som": 8333,
"Venezuelan Bolivar": 1010,
"Vietnamese Dong": 101100000101101
}
Note: CONVERSION_RATES is frozen.

```javascript
#1 Solution :
const vowels = ["A", "E", "I", "O", "U"];

const getConversionRate = (currency) => {
  const [firstLetter] = currency;
  const hasTechnicalDifficulties = !vowels.includes(firstLetter);

  const rate = CONVERSION_RATES[currency];
  return hasTechnicalDifficulties ? parseInt(rate, 2) : rate;
};

const convertMyDollars = (USD, currency) => {
  const amount = USD * getConversionRate(currency);
  return `You now have ${amount} of ${currency}.`;
};

#2 Solution :
const convertMyDollars = (usd, currency) => `You now have ${usd * parseInt(CONVERSION_RATES[currency], /[AEIOU]/.test(currency.charAt(0)) ? 10 : 2)} of ${currency}.`;

```

# By 3, or not by 3? That is the question . . .

A trick I learned in elementary school to determine whether or not a number was divisible by three is to add all of the integers in the number together and to divide the resulting sum by three. If there is no remainder from dividing the sum by three, then the original number is divisible by three as well.

Given a series of numbers as a string, determine if the number represented by the string is divisible by three.

You can expect all test case arguments to be strings representing values greater than 0.

Example:

"123" -> true
"8409" -> true
"100853" -> false
"33333333" -> true
"7" -> false

```javascript
const divisibleByThree = (str) =>
  str.split("").reduce((a, b) => parseInt(a) + parseInt(b)) % 3 === 0;
```

# In this Kata, you will remove the left-most duplicates from a list of integers and return the result.

// Remove the 3's at indices 0 and 3
// followed by removing a 4 at index 1
solve([3, 4, 4, 3, 6, 3]); // => [4, 6, 3]
More examples can be found in the test cases.

Good luck!

```javascript
const solve = (arr) => [...new Set(arr.reverse())].reverse();
```

# Unique string characters

In this Kata, you will be given two strings a and b and your task will be to return the characters that are not common in the two strings.

For example:

solve("xyab","xzca") = "ybzc"
--The first string has 'yb' which is not in the second string.
--The second string has 'zc' which is not in the first string.
Notice also that you return the characters from the first string concatenated with those from the second string.

More examples in the tests cases.

Good luck!

Please also try Simple remove duplicates

```javascript
const solve = (a, b) =>
  (a + b)
    .split("")
    .filter((c) => !a.includes(c) || !b.includes(c))
    .join("");
```

# Halving Sum

Task
Given a positive integer n, calculate the following sum:

n + n/2 + n/4 + n/8 + ...
All elements of the sum are the results of integer division.

Example
25 => 25 + 12 + 6 + 3 + 1 = 47

```javascript
const halvingSum = (n) => (n === 1 ? 1 : n + halvingSum(Math.floor(n / 2)));
```


# Target Date

You have an amount of money a0 > 0 and you deposit it with an interest rate of p percent divided by 360 per day on the 1st of January 2016. You want to have an amount a >= a0.

Task:
The function date_nb_days (or dateNbDays...) with parameters a0, a, p will return, as a string, the date on which you have just reached a.

Example:
date_nb_days(100, 101, 0.98) --> "2017-01-01" (366 days)

date_nb_days(100, 150, 2.00) --> "2035-12-26" (7299 days)

Notes:
The return format of the date is "YYYY-MM-DD"
The deposit is always on the "2016-01-01"
Don't forget to take the rate for a day to be p divided by 36000 since banks consider that there are 360 days in a year.
You have: a0 > 0, p% > 0, a >= a0


```javascript
function dateNbDays(a0, a, p) {
  let date = new Date(2016, 0, 1); 
  let days = 0;
  while (a0 < a) {
    a0 += (a0 * (p / 100)) / 360;
    days++;
  }

  date.setDate(date.getDate() + days); 
  
  return date.toISOString().split("T")[0];
}
```