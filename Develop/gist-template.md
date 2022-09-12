# Regex Tutorial

I have developed a tutorial detailing how regex is used so that other people learning regex can understand the search pattern the regex utilizes.
## Summary

A regular expression also known as regex, is a sequence of characters that specifies a search pattern in text. These patterns are used by string-searching algorithms for "find" or "find and replace" operations on strings, or for input validation. 

I will be describing a string of code using regex, the code is for matching an HTML tag.
`/^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/`

The table of contents will outline each section of this code and how it works.

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
* `^abc$` - ^start/$end of the string
    *`^` Matches the starting position within the string. In line-based tools, it matches the starting position of any line. 
    * `$` Matches the end of the string, or the end of a line if the multiline flag (m) is enabled. This matches a position, not a character.

### Quantifiers
* a*a+a? -0 or more, 1 or more, 0 or 1

* "+" Matches 1 or more of the preceding token.
* "*" Matches 0 or more of the preceding token.
* "?" Matches 0 or 1 of the preceding token, effectively making it      optional.
* "?" Makes the preceding quantifier lazy, causing it to match as few characters as possible. By default, quantifiers are greedy, and will match as many characters as possible.
* a{5}a{2,} -Looks for exactly five, two or more

* {2,6} -forces the input of characters between two & six characters long.

* a+?a{2,}? -match as few as possible

* ab|cd -match ab or cd

### Grouping Constructs
* (ABC) Capturing groups multiple tokens together and creates a capture group for extracting a substring or using a backreference.
* (?<name>ABC) named capturing group captures groups of a specific name.
* \1 is a numeric Referance
* (?:ABC) Groups multiple tokens together without creating a capture group
### Bracket Expressions
* A bracket expression represents a character set via a list of characters enclosed by the square brackets: '[' and ']'. It normally matches the target string with any single character from the list.
If the character list begins with '^', it matches any single character not from the rest of the list.

* `a-c-e`- If two characters in the list are separated by '–', this is shorthand for the (inclusive) range of characters between those two. It is illegal for two ranges to share an endpoint, 
* – is literal at the end or beginning of a bracket expression
* ^ is literal if not at the beginning of a bracket expression

### Character Classes

### The OR Operator

### Flags

### Character Escapes

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
