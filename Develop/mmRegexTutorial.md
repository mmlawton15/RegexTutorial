# MM's Regex Tutorial
Hello, and welcome to my Regex Tutorial for matching an email value.

## Summary
In this tutorial, I will explain the syntax of matching an email value using Regex, or regular expressions. The expression I will be using is below. At the end of this tutorial, you will be able to read and understand what this line of code is looking for and means. Happy coding!
- /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

## Table of Contents
- [Anchors](#anchors)
- [Boundaries](#boundaries)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [Quantifiers](#quantifiers)
- [Greedy and Lazy Match](#greedy-and-lazy-match)


## Regex Components
Below you'll find a list of different Regex Components that exist, along with explanations and examples. I have structured the below chapters to be in the order you read my Regex example from left to right. For the most part, we will be using the example mentioned in the smmary above, but Regexes are incredibly versatile and can be used in multiple different ways! All regex strings begin and end with /.


### Anchors
An anchor helps identify the beginning and the end of an expression. There are different ways to notate an anchor, but in this example we will be using `^` and `$` symbol. The `^` is the first symbol after the forward slash, meaning the code can expect the expression to follow until a `$` is found. You will see in our email example that we have a `^` at the beginning of the code, and a `$` at the end of the code. There is an additional simplified example of javascript below as well.
- /`^`([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})`$`/

```js
const regexTestOne = 'Colorado is really pretty'
console.log(/pretty$/.test(regexTestOne));
//Returns true, because the string ends with pretty.
const regexTestOne = 'Colorado'
console.log(/z$/.test(regexTestOne));
//Returns false because the string doesn't end with z.
const regexTestOne = 'Colorado'
console.log(/^C/.test(regexTestOne));
//Returns true because the string begins with a C.
```


### Grouping and Capturing
Capturing groups in Regex is defined by parentheses (). This is so the code associates symbols and letters together and can compartmentalize them in preparation for matching. In our example, we have 3 groups, `([a-z0-9_\.-]+)`, `([\da-z\.-]+)` and `([a-z\.]{2,6})`. To break this down:
1. The first group is for the characters that happen before the @ symbol. The + sign is the last symbol in this group, meaning that it only applies to the characters that are in this group. 
2. The second group is after the @ symbol, and would apply to the domain name, for example first_last@apple.com. 
3. The third group would be for the .com, .org, .edu, .co etc.
- /^`([a-z0-9_\.-]+)`@`([\da-z\.-]+)`\.`([a-z\.]{2,6})`$/

```js
const regexTestTwo = /([a-z0-9]+)/;
console.log("al1ae0p3".match(regexTestTwo));
//this would return true because the above regex expression takes any combination of letters a-z and digits 0-9, due to the + after the group
```


### Bracket Expressions
Brackets are used to determine what characters, digits and symbols are in a string. Because our example has a-z and 0-9 inside the brackets, this expression will accept any letter in the alphabet and single digit. The + sign outside of the bracket means we can have any number of  letters or digits in the string. This is important, because brackets are usually exclusive in the way they accept a single digit/character. In our example, we have 3 brackets (in groups mentioned above). 
1. Bracket 1 accepts any letter a-z, any number 0-9, and any of these symbols: \, ., _, -. The plus sign allowes duplicates of these! 
2. Bracket 2 accepts any single digit, any letter from a-z, and any symbol \, ., -. Again, the plus sign allows for multiple of these characters.
3. Bracket 3 includes any letter a-z, and either the . or the \ symbol.
- /`^`([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})`$`/

```js
const regexTestThree = /[a-z]/
console.log(regexTestThree)
//this would accept any single letter a-z
const regexTestThree = /([a-z]+)/
console.log(regexTestThree)
//this would accept any number of letters a-z
```


### Character Classes
Character classes for Regexes describe what kind of characters are accepted in the string. In this email example, the regex will accept any lowercase letters (a-z) and any digits (0-9). The \d snippent of code after the @ symbol means it will accept a single digit, for example first.last@1email.com. There is an additional example of what this looks like in javascript below:
- /^([`a-z0-9`_\.-]+)@([`\da-z`\.-]+)\.([`a-z`\.]{2,6})$/

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


### Quantifiers
Quantifiers determine how many time a character, symbol or digit appears in an expression. Quantifier symbols include *, ?, {, }, and +. These symbols mean different amounts, but in our example you see `+` appear twice, both following character classes. You will also see {2, 6} near the end of the expression.
1. Our first example of + is after the first 15 characters of the expression. This means this expression will accept any letters a-z, and digits 0-9, and the symbols _, \, ., and - any numbers of times. This is common for emails, as many people will do first.last@email.com or first_last_1@email.com.
2. Our second example of + appearing is 11 characters after the @ symbol. What this one means is that this expression will match any single digit, any letter a-z, and \, ., and - any number of times.
3. The {2,6} near the end of the expression applies to the bracket right before it, meaning it will accept any combination of letters from a-z and a \ or . at least 2 times, at most 6. An example that would satisfy this argument would be first.last@usc.com. 
- /^([a-z0-9_\.-]`+`)@([\da-z\.-]`+`)\.([a-z\.]{2,6})$/

```js
const regexTestFour = /^([0-9]+){10,50}$/
//this would require a string of digits, at least 10 in length but at most 50 in length.
```


### Greedy and Lazy Match
Greedy and Lazy Match have to do with quantifiers. Greedy match examples are +, *, ?, {}, as these accept as much/many different kinds of characters/digits/symbols as they can. They only return what is needed to match the expression, hence why they are referred to as greedy. Lazy Match examples only repeat as many times as needed to match the regex expression, and are notated by a ? after a +, *, or ?.
- /`^`([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})`$`/

```js
const regexTestFive = /([A-Z])*/
//this would try to match zero or more times, making it greedy because it accepts any amount of tries
const regexTestSix = /([A-Z])?/
//this is lazy and would try to match only zero or one time
```


## Author
Hi! Thanks for reading. My name is Mary Margaret and I am the author of this tutorial. I am an inquisitive student with a humble sense of humor and a positive demeanor. I enjoy trying new foods, visiting new places, tending to my many plants, and spending time with friends and family. I am using this bootcamp to sharpen my skills in preparation for a job in technology. I studied graphic design in college, which gives me an eye for front end design, but enjoy doing what it takes to make the backend work as well. You can find me at my GitHub Repository (https://github.com/mmlawton15).
