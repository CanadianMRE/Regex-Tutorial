# Title Regex Tutorial

This is a brief tutorial on Regex

## Summary

This tutorial will go over various things in regex, shown in [Table of Contents](#table-of-contents)

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

### Anchors
Anchors are what defines where your expression starts. For example '^' would refer to the begining of the string, while '$' would refer to the end of the string.

There is also boundaries and delimiters which can be used in similar ways.

Boundaries are invisible points which occur before and after words.

Currently these are the following anchors:
- '/b' Word boundary (Start or end of a word)
- '/B' Not a word boundary (Not start of a word so middle of a word)
- '^' Begining of string (or line)
- '$' End of string (or line)

### Quantifiers
Quantifiers declare how many times your parameters show up. For example, '91*' would mean that the string has a 9, followed by 0 or any number of 1s.

You also have other quantifiers:
- '*' Matches 0 or more times
- '+' Matches 1 or more times
- '?' Matches 0 or 1 times
- '{n}' Matches exactly n times
- '{n,}' Matches at least n times
- '{n, m}' Matches from n to m times

### Grouping Constructs
Grouping constructs are defined by parenthesis and lets us access the specific data captured by the string. For example with the expression 'https?://(www\.)?(\w+)(\.\w+)', we could get any URL. But when the regex results are returned in a program, we can get each spot we defined a parenthesis. Depending on the language the prefix can be many things, in this case we will assume it is '$'. For this example we will use 'https://www.youtube.com'. In the case of a regex '$0' would be equal to 'https://www.youtube.com', $1 would be equal to 'www.', $2 would be equal to 'youtube' and $3 would be equal to '.com'.

### Bracket Expressions
Bracket expressions are defined using the '[' and ']' characters. Anything between these will be searched for on each section you look at.

### Character Classes
Bracket expressions, defined with a [Bracket Expression](#bracket-expressions) can be used to specify multiple variables. For example we can look for any string with any number of 'a', 'b', or 'c' digits, but no other digits using the following expression, '[abc]+'. You can get specific ranges of digits using expressions like the following '[a-zA-Z]', which would look for any lowercase and capital letters.

### The OR Operator
The OR operator, which uses the '|' character lets you look for multiple expressions on each item. So you could look for a string which has only digits OR only lowercase letters with the following expression, '\b[0-9]+|[a-z]+\b+'

### Flags
Regex only has 6 flags:
- 'i' means the search is case sensitive, meaning A and a are equal
- 'g' means that the search will return an array of all matches, rather then just the first match
- 'm' means that the search will count all lines rather then looking at each line seperate
- 's' enables 'dotall' mode which lets newline characters ('/n') be counted with the '.' operator
- 'u' enables 'full unicode support' [Read more here](https://javascript.info/regexp-unicode)
- 'y' enables 'sticky' mode [Read more here](https://javascript.info/regexp-sticky)

In an regex expression, these can be used like the following, 'we/gi'. This will look for any strings which match 'we' and it will ignore if the letters are uppercase or not since we declared the 'i' flag. It will also return all matches in an array rather then the first match since we declared the 'g' flag.

### Character Escapes
Character escapes can be used on any operator to use it as a literal. So for example instead of the '.' operator which means any character, we could do '\.' which would look for a literal '.' in the string.

## Author
This guide was made by Jaymen Laton ([Github](https://github.com/CanadianMRE))
