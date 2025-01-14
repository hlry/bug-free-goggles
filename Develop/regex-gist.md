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
Within /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ , the "^" and "$" symbols are anchors.

The carrot symbol "^" matches a string that starts with the symbol following the "^" symbol.

The money symbol "$" matches a string that ends with the symbol preceding the "$" symbol.

Here, this means that the anchors "^" and "$" will match a string beginning with the "(" following the carot "^" symbol and ending with the ")" preceding the dollar "$" symbol.

### Quantifiers

Within /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ , the "{}" symbols are anchors.

Other quantifiers such as "*" and "?" are not used in this regex expression.

In general, the "{" and "}" quantifiers following the pattern "abc{2,5}" match a string that has ab followed by 2 up to 5 c.

Here, that means that for "{2,6}", there is a lower limit of 2 and an upper limit of 6 of the preceding component.

### OR Operator

Within /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ , the "[]" symbols are "OR" operators.

Another OR operator in regex, "|", is not used here.

In general, the "[" and "]" OR operators indicate that pattern "a[bc]" matches a string that is followed by b or c, but without capturing b or c.

Here, the first OR operator, "[a-z0-9_\.-]" indicates that the preceding components "/^(" are followed by components any of the components included within the square brackets, but the contents of the square brackets are not captured.

Similarly, for "[\da-z\.-]" and "[a-z\.]", the components preceding the square brackets are followed by any of the components within the square brackets, without capturing those components.

### Character Classes

Within /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ , the "\d" and "." symbols are anchors.

Another two character classes in regex, "\w" and "\s", are not used here. Neither are the character class negations "\D", "\S", or "\W".

In general, the backslash lowercase d component, "\d", matches a single character that is a digit. You can play with matching numbers appearing in test strings here: https://regex101.com/r/cO8lqs/4

Here, in the context of "\d" being located within the square brackets, "[\da-z\.-]" (an OR Operator -- see above) tells us that it can match with a single character that is a digit or any other the other components in the square brackets.

This regex also uses "." In general, the "." character class can match with any character.

Here, "." is used within square bracket OR operators before the "@" symbol (see "([a-z0-9_\.-]+)@"), within square brackets after the "@" symbol, (see "@([\da-z\.-]+)"), and within square brackets after a dot after the preceding square brackets, (see ".([a-z\.]{2,6})").

This will match with any symbol before the "@" symbol, then after the "@" symbol, and then after a . following the preceding any matching symbol after the "@" symbol. 

In other words, it could match something like "a@4.com", which could conceivably be an email address.

### Flags

Within /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ , there are no regex flags.

In general, regex flags are indicated with a "g" for global, an "m" for multi-line, or an "i" for insensitive (to make the match case-insensitive). 

These characters are not present in this email matching regex.

### Grouping and Capturing

Within /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ , there are three capturing groups.

In general, parenthesis are used to create a capturing group. When there is a string, a group can access the values of the string in the form of an array.

Here, the following three groups are captured:
- ([a-z0-9_\.-]+) -- group A, preceding "@" symbol
- ([\da-z\.-]+) -- group B, following "@" symbol
- ([a-z\.]{2,6}) -- group C, following "." after group B

This matches onto the syntax of an email address. 
For example, in "xyz@abc.com," the group A would match with "xyz," group B would match with "abc," and group C would match with "com".

### Bracket Expressions


Within /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ , the "[" and "]" symbols indicate the bracket expressions.

In general, a string such as "abc" within brackets (e.g., [abc]), matches a string of any or either of the variables, alone or several in combination. 
For example, it could match "a" or "a b" or "a c." Similarly, a bracket containing 0-9 (i.e., [0-9]), could contain a numeral character -- alone or several in any combination -- between 0 and 9.

Here, there are three bracket expressions:
- [a-z0-9_\.-] -- bracket expression A
- [\da-z\.-] -- bracket expression B
- [a-z\.] -- bracket expression C

Each of these bracket expressions contains "a-z" and could match a string including one or more a-z letters in any order.

Interestingly, the first bracket expression A includes "0-9" within the brackets, and so the text prior to the "@" sign in an email address could match onto any numerical character in addition to string letters.

### Greedy and Lazy Match
Within /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ , there are no greedy or lazy operators.

In general, the quantifiers (* + {}) are greedy operators. 

The asterisk or star symbol is not present in this regex, and the curly brackets alone would not be a greedy operator.

### Boundaries
In general, boundaries are represented by backslash lowercase b "\b" or backslash uppercase B "\B".

These characters are not present in this email regex.

### Back-references
Within /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ , there are no back-references.

In general, back-references are indicated by a backslach following parentheses, such as ([abc])/1, or ([abc])([de])\2\1, or (?<foo>[abc])\k.

A back reference can be used as a sort of bookmark in order to label part of a regex and refer to it later. It could be labelled with a number ("1" or "2") or even with a name, such as <foo>.

Here, the backslash "\" symbol is used, but it does not follow parentheses and so it is not being used as a back reference.

### Look-ahead and Look-behind
Within /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ , there are no look-aheads or look-behinds.

Look-aheads and look-behinds match one thing only if it is followed by another thing (required bit), even if the required bit isn't part of the regex match.

In general, look-aheads and look-behinds are represented by recognizable combinations of parentheses, question mark, and equal signs or greater/less than signs.

For example, look-aheads and look-behinds will look like (?=) or (?<=). With characters added, it could be x(?=y) or (?=y)x. 
In this example, the "y" could be the required thing, so the regex only matches x if it is preceded or followed by y, but the y would not be a part of the overall regex match.

Here, none of this syntax is present in the email regex.

## Author

The author of this gist is an in-house attorney but this gist is expressing personal views and is not legal advice or representing the views of my employer.

The author created this regex tutorial as part of a javascript full stack immersion program.

For any questions about this gist please contact the author on GitHub: [HLRY](https://github.com/hlry) 
