# Regex 101

Regex stands for Regular Expression. Regex is a method on searching a text or multiple texts within a string.Regex can help in searching, validating and replacing text without having to go through each string manually. We will be learning the basics of regex in this tutorial and it is broken down into multiple sections to make it easier for reader to navigate through the tutorial

## Summary

In this tutorial we will be learning about the different components and functions that we can use to start our journey in searching through a string of text using regex.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components

Important thing to note is that a regex expression always starts with a `/` and ends with another  `/`.

### Anchors

Anchor symbols are:
`^` and `$`

`^` is used before a text when you want to match a string of text that starts with that specific text, whereas `$` is used after a text when you want to match a string of text that ends with that specific text. For example `/^a/` would match all text that starts with the letter a; on the other hand `/c$/` would match all text that ends with the letter c. In the example above, abc would match both expression, however cba would not.

### Quantifiers
Quantifiers symbols are:
`{x}`, `{x,y}`, and `{x, }`

They also have some shorthands:
`+`, `?`, and `*`

`{x}` is used to specify a how many characters you are looking to match. so `/e{2}/` will look for a pattern of 2 e's that sits right next to each other. The example above would match the text `bee` but would not match the text `beee` nor `be`.

`{x,y}` is used to specify the minimum (x) and the maximum (y) number of characters you are looking to match. So `/e{2,4}` will look for a pattern of 2 e's up to 4 e's that sits next to each other. The example above would match the text `bee`, `leee`, and `weeee`. However once the number of e's next to each other is outside the quantifier numbers such as `be` or `weeeee`, it will not match.




### Grouping Constructs

### Bracket Expressions

### Character Classes

### The OR Operator

### Flags

### Character Escapes

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
