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
* \1 is a numeric reference
* (?:ABC) Groups multiple tokens together without creating a capture group
### Bracket Expressions
* A bracket expression represents a character set via a list of characters enclosed by the square brackets: '[' and ']'. It normally matches the target string with any single character from the list.
If the character list begins with '^', it matches any single character not from the rest of the list.

* `a-c-e`- If two characters in the list are separated by '–', this is shorthand for the (inclusive) range of characters between those two. It is illegal for two ranges to share an endpoint, 
* – is literal at the end or beginning of a bracket expression
* ^ is literal if not at the beginning of a bracket expression

### Character Classes
Character classes match a character from a specific set. There are a number of predefined character classes and you can also define your own sets.

* [ABC] Characters inside brakets will match "a", "b", or "c". 
* [^ABC] Adding a caret will match any character that is not in the set.
* [A-Z] Add a dash between two characters will select a Range.[a-z] specifies a range which matches any lowercase letter from "a" to "z". These forms can be mixed: [abcx-z] matches "a", "b", "c", "x", "y", or "z", as does [a-cx-z]
* .  Will Match any characters expect linebreaks. Its like a wildcard and will accpet any input.
* [\s\S] A character set that can be used to match any character, including line breaks, without the dotall flag. An alternative is [^] carrot in brackets, but it is not supported in all browsers.
* \w Matches any word character (alphanumeric & underscore). Only matches low-ascii characters (no accented or non-roman characters).
* \W Matches any character that is not a word character (alphanumeric & underscore).
* *d Matches any digit character (0-9)
* \p Matches a character in the specified unicode category.

### The OR Operator
* | Acts like a boolean OR. Matches the expression before or after the | It can operate within a group, or on a whole expression. The patterns will be tested in order. Just as in java will match either set of characters. It will look for this OR that.
### Flags
* A regular expression consists of a pattern and optional flags: g, i, m, u, s, y. Without flags and special symbols (that we’ll study later), the search by a regexp is the same as a substring search.
* `i` ignores case
* `g` Global search retain the index of the last match, allowing following searches to start from the end of the previous match. Without global flag, all searches will return the same match. 
* `m` Multiline flag, when enabled, beginning and end anchors (^ and $) will match the start and end of the line, instead of the start and end of the string. 
* `u` Unicode, enables full Unicode support. This flag enables correct processing of surrogate pairs. 
* `y` "Sticky" mode: searching at the exact position and ingnores the global (g) flag if set. 
* `s` enables "dotall" mode that allows dot (.) to match any character, including newline (\n).


### Character Escapes
To match a character having special meaning in regex, you need to use a
* `(\)` escape sequence prefix with a backslash  \. matches "."; regex \+ matches "+"; and regex \( matches "(".
* `\\` Use regex \\ to match "\" (back-slash)
* `n` newline escape sequence
* `\t` for tab
* `\r` for carriage-return
* `\nnn` for a up to 3-digit octal number
* `\xhh` for a two-digit hex code,
* `\uhhhh` for a 4-digit Unicode 
* `\uhhhhhhhh` for a 8-digit Unicode



## Author

Emily McEwen: The Ohio State University Full Stack Bootcamp Student

### Sources and References
* `https://www.regular-expressions.info/charclass.html`
* `https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions/Cheatsheet`
* `https://medium.com/factory-mind/regex-tutorial-a-simple-cheatsheet-by-examples-649dc1c3f285`
* `https://en.wikipedia.org/wiki/Regular_expression`

My Github: `https://github.com/emmcewen`
