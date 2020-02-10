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
const countLettersAndDigits = input => input.replace(/[^a-z\d]/gi, "").length;
```
