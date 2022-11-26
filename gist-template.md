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

Anchor expressions are:
`^` and `$`

`^` is used before a text when you want to match a string of text that starts with that specific text, whereas `$` is used after a text when you want to match a string of text that ends with that specific text. For example `/^a/` would match all text that starts with the letter a; on the other hand `/c$/` would match all text that ends with the letter c. In the example above, abc would match both expression, however cba would not.

### Quantifiers

Quantifiers expressions are:
`{x}`, `{x,y}`, and `{x, }`

They also have some shorthands:
`+`, `?`, and `*`

`{x}` is used to specify a how many characters you are looking to match. so `/e{2}/` will look for a pattern of 2 e's that sits right next to each other. The example above would match the text `bee` but would not match the text `beee` nor `be`.

`{x,y}` is used to specify the minimum (x) and the maximum (y) number of characters you are looking to match. So `/e{2,4}/` will look for a pattern of 2 e's up to 4 e's that sits next to each other. The example above would match the text `bee`, `leee`, and `weeee`. However once the number of e's next to each other is outside the quantifier numbers such as `be` or `weeeee`, it will not match.

`{x, }` is similar to the expression above, the difference is that the maximum or upper limit is not set. therefore it will just look for the minimum number of characters and match them. So `/e{2, }/` will match texts that has at least 2 e's that sits next to each other such as `bee` or `beeeeeeeeeeeeeeeeeeeeeee` as there are no upper limit. It would not match `be` as it is below the minimum limit.

`+` is the shorthand for `{1, }`. So `/e+/` would match `be` and `beeeeeeeee`.

`?` is the shorthand for `{0,1}`. So `/colou?r/` would match both `color` and `colour`, but would not match `colouur` as the letter u has a minimum limit of 0 and maximum limit of 1, which means it can be non-existent and it would still match the letters that comes before the `u`.

`*` is the shorthand for `{0, }`. So `//colou*r//` would match `color` and `colouuuuur` as there are no upper limit.

### Grouping Constructs

Grouping constructs expressions are:
`[...]` and `[a-z]` or `[0-9]`

`[...]` is called sets and is used to match any of the character put inside the square bracket. So `/[ctpf]ar/` would match `car`, `tar`, `par`, and `far`.

`[a-z]` or `[0-9]` is called ranges and is used to match a range of character specified in the bracket. 

If you want to negate a range or negate a set, you just need to put the `^` at the start of the inside of the square bracket. So `/[^abcd]/` would match strings of text that doesn't have a, b, c, or d in it.

`\w` is the shorthand for `[a-zA-Z0-9]`


`\d` is the shorthand for `[0-9]`
`\D` is the shorthand for `[^0-9}`

### Bracket Expressions

### Character Classes

### The OR Operator

### Flags

### Character Escapes

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
