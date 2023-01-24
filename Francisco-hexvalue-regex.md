# Title Regex matching Hex value

Regular expressions are combination of especial character operators, which are symbols that control a specific search, that you can use to construct search strings for advanced find and or replace searches.

## Summary

I will be covering the components of a regular expressions used to match Hex Values. Hexadecimal is a numbering system with a base 16 it can be used to represent a large numbers with fewer digits. In this system there are 16 symbols or possible digit values form 0-9 followed by six alphabetic characters - a,b,c,d,e and f. On programing we can use the hex value to represent a color in RGB format by combining three values - the amounts of red, green and blue in a particular shade of color.
These color hex codes have been an integral part of HTML for web design, and remain a key way of representing color formats digitally.
By contrast, the hexadecimal format is only six character long. In that sense, it compresses the individual RGB values into one six-digit value that uses a combination of alphanumeric characters including letters and numbers to identify a color.

A hexadecimal color value is a six-digit code preceded by a # sign; it defines a color that is used in a website or a computer program.

`/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`

## Table of Contents

- [Title Regex matching Hex value](#title-regex-matching-hex-value)
  - [Summary](#summary)
  - [Table of Contents](#table-of-contents)
  - [Regex Components](#regex-components)
    - [Anchors](#anchors)
    - [Quantifiers](#quantifiers)
    - [Bracket Expressions](#bracket-expressions)
    - [Character Classes](#character-classes)
    - [The OR Operator](#the-or-operator)
  - [Author](#author)

## Regex Components

### Anchors

Anchors have a special meaning in regular expressions they do not match any character. Instead, they match a position before o after characters:

/`^`#?([a-f0-9]{6}|[a-f0-9]{3})`$`/

    ^ - The caret anchor matches the beginning of the text
    $ - The dollar anchor marches the end of the text.

![](assets/Screen%20Shot%202023-01-23%20at%2010.26.19%20AM.png)
You should find that regex matches the first string but not the last three.

![](assets/Screen%20Shot%202023-01-23%20at%2010.29.27%20AM.png)
You should find that regex marches the last string

### Quantifiers

Quantifiers specify how many instances of character, group, or character class must be present int the input for a match to be found.
By default quantifiers are greedy, and will match as many characters as possible.

/^#`?`([a-f0-9]`{6}`|[a-f0-9]`{3}`)$/

If the symbols "+,?,{}" characters are found with regular expressions, they are considered quantifiers, The `?` indicates the expression to match between 0 or 1 time, The `+` indicates if matches one or more.
In our Hex value regular expression we have {6} (hex triplet format) and {3} (shorthand Hex Format), this indicates that the length of the component preceding these quantifiers should be 6 for {6} and 3 for {3}

![](assets/Screen%20Shot%202023-01-23%20at%2010.55.28%20AM.png)
Using regex you can match the spelling of the word 'catt'

![](assets/Screen%20Shot%202023-01-23%20at%2010.58.46%20AM.png)

On this case you can match the spelling of the word 'cattt'

### Bracket Expressions

/^#?`([a-f0-9]`{6}|`[a-f0-9]`{3})$/

A bracket expression (a expression enclosed in square brackets []) It shall match a specific set of single characters, and may match a specific set of multi-character collating elements, based on the non-empty set of list expressions contained in the bracket expression.

![](assets/Screen%20Shot%202023-01-23%20at%2011.09.00%20AM.png)
`[abcd]` Matches any character in the square brackets

![](assets/Screen%20Shot%202023-01-23%20at%2011.09.00%20AM.png)
[a-d] - Matches any character in the range of characters separated by hyphen

### Character Classes

/^#?(`[a-f0-9]`{6}|`[a-f0-9]`{3})$/

Character classes are components within our regular expression that tells us what type of character to expect. In our example our character classes are confined with brackets []. For example we have 2 characters classes: [A-F0-9] and [a-f0-9] which searches for the same values.

![](assets/Screen%20Shot%202023-01-24%20at%209.21.46%20AM.png)

[a-f0-9] Matches a minus letter in the range of "a" to "f" and a number in the range of "0" to "9"

![](assets/Screen%20Shot%202023-01-24%20at%209.21.46%20AM.png)

[A-F0-9] Matches all capital letters in the range of "A" to "F" and a number in the range of "0" to "9"

### The OR Operator

/^#?([a-f0-9]{6} `|` [a-f0-9]{3})$/

The or operator on regex is defined using the `|` element, the or operator indicates that it could either of the components that we are separating with |. Our operator its separating 2 components this means our hex value could either be 6 character [a-f0-9]{6} or 3 character [a-f0-9].

![](assets/Screen%20Shot%202023-01-24%20at%209.33.38%20AM.png)

## Author

Hi im Francisco Sanchez, Im a full-stack developer student trying to success and dominate the front-end and back-end.
GitHub: MXCAZ
