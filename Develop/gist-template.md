# MM's Regex Tutorial
Hello, and welcome to my Regex Tutorial for matching an email value.

## Summary
In this tutorial, I will explain the syntax of matching a an email value using Regex, or regular expressions. The expression I will be using is below. At the end of this tutorial, you will be able to read and understand what this line of code is looking for and means. Happy coding!
- /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components
Below you will find a list of different Regex Components that exist, along with explanations and examples. For the most part, we will be using the example mentioned in the smmary above, but Regexes are incredibly versatile and can be used in multiple different ways! All regex strings being and end with /.

### Anchors
An anchor helps identify the beginning and the end of a string. There are different ways to notate an anchor, but in this example we will be using `^` and `$` symbol. The `^` is the first symbol after the forward slash, meaning the code can expect a string to follow until it encounters a `$`. You will see in our email example that we have a `^` at the beginning of the code, and a `$` at the end of the code.
- /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

### Quantifiers

### OR Operator

### Character Classes
Character classes for Regexes describe what kind of characters are accepted in the string. In this example, the regex will accept any lowercase letters a-z.  Here is an example of what this looks like in javascript:

```js
const regex = /[a-z]/
console.log(regex.test("supercalifragilisticexpialidocious"))
//this would log true, because all of the characters in this string are lowercase letters
console.log(regex.test("Periwinkle"))
//this would log false, due to the uppercase letter
```

### Flags

### Grouping and Capturing

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author
Hi! Thanks for reading. My name is Mary Margaret and I am the author of this tutorial. I am an inquisitive student with a humble sense of humor and a positive demeanor. I enjoy trying new foods, visiting new places, tending to my many plants, and spending time with friends and family. I am using this bootcamp to sharpen my skills in preparation for a job in technology. I studied graphic design in college, which gives me an eye for front end design, but enjoy doing what it takes to make the backend work as well. You can find me at my GitHub Repository (https://github.com/mmlawton15).
