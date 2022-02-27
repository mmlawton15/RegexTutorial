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
- /`^`([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})`$`/


### Quantifiers
Quantifiers determine how many time a character, symbol or digit appears in an expression. Quantifier symbols include *, ?, {, }, and +. These symbols mean different amounts, but in our example you see `+` appear twice, both following character classes. 
1. Our first example of + is after the first 15 characters of the expression. This means this expression will accept any letters a-z, and digits 0-9, and the symbols _, \, ., and - any numbers of times. This is common for emails, as many people will do first.last@email.com or first_last_1@email.com.
2. Our second example of + appearing is 11 characters after the @ symbol. What this one means is that this expression will match any single digit, any letter a-z, and \, ., and - any number of times.
- /^([a-z0-9_\.-]`+`)@([\da-z\.-]`+`)\.([a-z\.]{2,6})$/


### Character Classes
Character classes for Regexes describe what kind of characters are accepted in the string. In this email example, the regex will accept any lowercase letters (a-z) and any digits (0-9). There is an additional example of what this looks like in javascript below:
- /^([`a-z0-9`_\.-]+)@([\d`a-z`\.-]+)\.([`a-z`\.]{2,6})$/

```js
const regexOne = /[a-z]/
console.log(regexOne.test("supercalifragilisticexpialidocious"))
//this would log true, because all of the characters in this string are lowercase letters
console.log(regexOne.test("Periwinkle"))
//this would log false, due to the uppercase letter

const regexTwo= /[A-Z0-9]/
console.log(regexTwo.test("Bananas1"))
//this would return false because there are lowercase letters included
console.log(regexTwo.test("CHAOTICLETTERS12"))
//would return true because it is all capitals and digits.
console.log(regexTwo.test("ALPHABET"))
//would also return true, although no digits are present because there is only uppercase letters.
```


### Grouping and Capturing
Catching groups in Regex is defined by parentheses (). This is so the code associates symbols and letters together and can compartmentalize them in preparation for matching. In our example, we have 3 groups, `([a-z0-9_\.-]+)`, `([\da-z\.-]+)` and `([a-z\.]{2,6})`. To break this down, the first group is for the characters that happen before the @ symbol. The + sign is the last symbol in this group, meaning that it only applies to the characters that are in this group. The second group is after the @ symbol, and would most likely apply to the name of a company, for example first_last@apple.com. The third group would be for the .com, .org, .edu etc.
- /^`([a-z0-9_\.-]+)`@`([\da-z\.-]+)`\.`([a-z\.]{2,6})`$/

### Bracket Expressions


### Greedy and Lazy Match


### Boundaries


### Back-references


### Look-ahead and Look-behind


## Author
Hi! Thanks for reading. My name is Mary Margaret and I am the author of this tutorial. I am an inquisitive student with a humble sense of humor and a positive demeanor. I enjoy trying new foods, visiting new places, tending to my many plants, and spending time with friends and family. I am using this bootcamp to sharpen my skills in preparation for a job in technology. I studied graphic design in college, which gives me an eye for front end design, but enjoy doing what it takes to make the backend work as well. You can find me at my GitHub Repository (https://github.com/mmlawton15).
