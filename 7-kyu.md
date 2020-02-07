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

function removeDuplicateWords (s) {
  return [...new Set(s.split(' '))].join(' ');
}
```
