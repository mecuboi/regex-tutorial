# Regex Javascript 101

Regex stands for Regular Expression. Regex is a method on searching a text or multiple texts within a string.Regex can help in searching, validating and replacing text without having to go through each string manually. We will be learning the basics of regex in this tutorial and it is broken down into multiple sections to make it easier for reader to navigate through the tutorial

## Summary

In this tutorial we will be learning about the different components and functions that we can use to start our journey in searching through a string of text using regex.

The regex that we will be looking at is the regex to match an email:

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Sets and Ranges](#sets-and-ranges)
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

In the email example we can see that the anchor tag is used in the beginning and end of the expression:
/`^`([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})`$`/

This means that the expression expects the string to start with the `[a-z0-9_\.-]+` requirement and end with the `[a-z\.]{2,6}` requirement. We will learn more detail below as to what these expressions mean.

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

in the email example we can see the quantifier here: /^([a-z0-9_\.-]`+`)@([\da-z\.-]`+`)\.([a-z\.]`{2,6}`)$/

The `+` is to allow the first 2 sections of the expression (before and after @) to have at least 1 character and no upper limit.

In the final section of the email string (after .), there is a minimum of 2 characters and a maximum of 6 characters required that is within the `[a-z\.]` rule. In real life example this would mean the ".com / .net / .com.au / etc."



### Sets and Ranges

Bracket expressions are:
`[...]` and `[a-z]` or `[0-9]`

`[...]` is called sets and is used to match any of the character put inside the square bracket. So `/[ctpf]ar/` would match `car`, `tar`, `par`, and `far`.

`[a-z]` or `[0-9]` is called ranges and is used to match a range of character specified in the bracket. 

If you want to negate a range or negate a set, you just need to put the `^` at the start of the inside of the square bracket. So `/[^abcd]/` would match strings of text that doesn't have a, b, c, or d in it.

In the email example we can see the sets and ranges here in multiple sections: /^(`[a-z0-9_\.-]`+)@(`[\da-z\.-]`+)\.(`[a-z\.]`{2,6})$/

This sets and ranges within the multiple sections of the expression ensures that the correct characters is inputted within the email restriction. 

`[a-z0-9_\.-]` ensures that this section is inputted with lowercase alphanumeric and special characters: _, ., -

`[\da-z\.-]` ensures that this section is inputted with `\d` = digits, a-z alphabets and special characters: _, ., -

`[a-z\.]`ensures that this section is inputted with a-z alphabets and special characters: _, ., -


### Character Classes

Here are the list of Character Classes:

`\w` is the shorthand for `[a-zA-Z0-9_]`

`\d` is the shorthand for `[0-9]`

`\s` is to match a single whitespace symbol like space, a tab (\t), and a newline (\n)

Here are the list of inverse Character Classes:

`\W` is the shorthand for `[^a-zA-Z0-9}`

`\D` is the shorthand for `[^0-9}`

`\S` is to match everything except for a single whitespace symbol like space, a tab (\t), and a newline (\n)

In the email example we can see the character classes here in multiple sections: /^([a-z0-9_\.-]+)@([```\d```a-z\.-]+)\.([a-z\.]{2,6})$/

`\d` is the short hand to ensure that numeric numbers is allowed in this section.

### The OR Operator

The OR operator expression is:

`x|y`

The `|` expression function as an or method. So `a|c` means either the text contains a or c. We can use parentheses to specify a specific portion of the text.
`/cent(er|re)/` will match both center and centre.

without the paranthese it will treat the 2 side as individual words.
`/center|re/` will match either center or re.

There are no OR operator in the email example.

### Flags

Flags are used to command the search extent or behaviour of our expression. It is normally placed after the end `/` of an expression. For example: `/search/g`

Here are the list of flags:

`g`: matches the entire strings of text (also can be considered g for global)

`i`: makes the expression case insensitive

`m`: enables multi-line mode (enabling `^` and `$` to match the beginning and ending of every single line instead of the whole string)

`u`: enables support for unicode

`s`: causes `.` to also match new line characters 

These rules can be inserted in the email requirement by adding it at the end after the `/` expression: /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`g`

### Character Escapes

Escaping a character means you want to search that particular character in your search expression, however they are normally part of the expression function or method. For example `()` is a part of the expression function and therefore will not be thought of as a search criteria. To "escape" the character, you need to put a `\` before the character. So to match a text saying: "test()", you need to use this expression: `/test\(\)/`

In the email example we can see the sets and ranges here in multiple sections: /^([a-z0-9_```\.```-]+)@([\da-z```\.```-]+)```\.```([a-z```\.```]{2,6})$/

`\.` is to allow `.` in this section.

## Author

My name is Matthew and I am a student at USYD's bootcamp in full stack engineering. Follow my github at [@mecuboi](https://github.com/mecuboi)
