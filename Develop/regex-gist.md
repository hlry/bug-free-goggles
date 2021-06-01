# Regex Tutorial

This gist provides an explanation of a regular expression or "regex."

The following sectins will walk through the specific components of the regex and what they do.

## Summary

The following regular expression can be used to verify that user input is a valid email address: 

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

But how?

Read on to find out. 

Regex is sort of like a puzzle that you have to decode.

Each character of this regular expression ensures that the user has entered characters before and after an "@" symbol, and that the characters after the "@" symbol are a domain (e.g., hotmail.com, aol.com, yahoo.co.uk, @googlemail.com, etc.).

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
The email detection regex /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ can be broken down into components.

### Anchors
Within /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ , the "^" and "$" symbols can be anchors.

The carrot symbol "^" matches a string that starts with the symbol following the "^" symbol.

The money symbol "$" matches a string that ends with the symbol preceding the "$" symbol.

Here, this means that the anchors "^" and "$" will match a string beginning with the "(" following the carot "^" symbol and ending with the ")" preceding the dollar "$" symbol.

### Quantifiers

Within /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ , the "{}" symbols can be anchors.

Other quantifiers such as "*" and "?" are not used in this regex expression.

In general, the "{" and "}" quantifiers following the pattern "abc{2,5}" match a string that has ab followed by 2 up to 5 c.

Here, that means that for "{2,6}", there is a lower limit of 2 and an upper limit of 6 of the preceding component.

### OR Operator

Within /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ , the "[]" symbols can be "OR" operators.

Another OR operator in regex, "|", is not used here.

In general, the "[" and "]" OR operators indicate that pattern "a[bc]" matches a string that is followed by b or c, but without capturing b or c.

Here, the first OR operator, "[a-z0-9_\.-]" indicates that the preceding components "/^(" are followed by components any of the components included within the square brackets, but the contents of the square brackets are not captured.

Similarly, for "[\da-z\.-]" and "[a-z\.]", the components preceding the square brackets are followed by any of the components within the square brackets, without capturing those components.

### Character Classes

### Flags

### Grouping and Capturing

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

The author of this gist is an in-house attorney but this gist is expressing personal views and is not legal advice or representing the views of my employer.

The author created this regex tutorial as part of a javascript full stack immersion program.

For any questions about this gist please contact the author on GitHub: [HLRY](https://github.com/hlry) 
