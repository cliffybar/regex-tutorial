# Regex Tutorial

Writing properly working code cannot be done without first understand how the code itself functions. By understanding why a code is written in its unique sequence, a developer will be better equipped when tasked to explain theirs or others' code.

</br>

## Summary

Regular expressions, also known as regex, are a sequence of characters that define a specific search pattern. When included in code or search algorithms, a regex can be used to find certain patterns of characters within a string, or to find and replace a character or sequence of characters within a string.

In my regex tutorial, I will be describing matching an email:

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

</br>

## Table of Contents

- [Overview](#overview)
- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)

</br>

## Regex Components

### Overview

An example for an email regex is as follows: `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

To make this example more user-friendly, think of it in three groups:

1. Username: `/^([a-z0-9_\.-]+)@`
    
    A username can accept values ranging from letters between `a-z`, numbers between `0-9`, the underscore `_` character, the period `.` character, and the hyphen `-` character. An example would be `clifford_crowell@domain.extension`, or `clifford.crowell@domain.extension`.

2. Email domain: `([\da-z\.-]+)\.`
    
    An email domain can accept values ranging from a single digit between `0-9`, letters between `a-z`, the period `.` character, and the hyphen `-` character. An example would be `username@10gmail.extension`. 

3. Extension: `([a-z\.]{2,6})$/`
    
    An extension can accept values ranging from letters between a-z and the period `.` character, and cannot be `less than 2 or more than 6` characters long. An example would be `username@domain.com`.

</br>

### Anchors

1. `^` : Matches the beginning of the string, or the beginning of a line if the multiline flag (m) is enabled. This matches a position, not a character.

    If we have an email address of `clifford_crowell@gmail.com`, the search MUST and can only begin with the `c` in the email username. 

2. `$` : Matches the end of the string, or the end of a line if the multiline flag (m) is enabled. This matches a position, not a character.

    If we have an email address of `clifford_crowell@gmail.com`, the search MUST and can only end with the `u` in the extension. 

</br>

### Quantifiers

1. `+` : Matches 1 or more of the preceding token for an unlimited number of times. 

    We have an email username validator of `/^([a-z0-9_\.-]+)@`. If we have an email address of `clifford_crowell@gmail.com`, the email address can be written as  `clifford_crowell.lex_luthor@gmail.com` or `superman_batman-wonderwoman@gmail.com` and the search will still recognize the repeating of tokens because the `+` quantifier is matching the entire set and will continue to match the entire set UP to the literal `@` sign. The username validator will then not validate the email domain and extension.

2. `{}` : Matches the specified quantity of the previous token.

    The string length will be determined by what is inside the curly braces `{}` cannot go outside of the limits unless specified otherwise. For example, `{2,6}` means `less than 2 or more than 6` characters long. For an email extension, this means `username@domain.com` is acceptable because `3` characters long is within the upper and lower limits. However, `username@domain.comcomcom` is not acceptable is `9` characters long is outside of the upper limit. If the limit is `{2,}`, this means there is only a lower limit of `2`. Then, this would accept `username@domain.comcomcom`. 

</br>

### Character Classes

1. `\d` : Matches any single digit character (0-9). Equivalent to [0-9].

    Ex. Think of the text string `ab2 ab34 ab5 ab67`. The character class `\d` will match `2`, `3`, `4`, `5`, `6`, and `7` all as individual digits despite `34` and `67` being one right after the other.

</br>

### Grouping and Capturing

1. `()` : Groups multiple tokens together and creates a capture group for extracting a substring or using a backreference.
    
    Ex. Username group is `([a-z0-9_\.-]+)`, email domain group is `([\da-z\.-]+)`, and extension group is `([a-z\.]{2,6})`. 

</br>

### Bracket Expressions

1. `[]` : Match any character in the set.

    Ex. `[a-z]` and `[0-9]` in the Username group means that the username may allow characters between letters a through z and numbers between 0 through 9 to be included in the username. This can also be applied to literals which is indicated with a forward slash `\`. For example, we can the following `([a-z0-9\.\+]+)` as an email username validator. In this example, we can match for `[a-z]` and `[0-9]`, but also the literal characters of `.` and `+`. So, an email could like look `clifford.97@domain.extension` and all characters will be matched. 

</br>

### Greedy and Lazy Match

`+` and `{}` are both greedy and lazy matches. This is because both will match as many characters infinitely. Although `{}` can only do this should no upper limit exist, it will otherwise as many characters possible. 

</br>

## Author

Hello! My name's Clifford and I currently work as a State & Local Tax Analyst for Ernst & Young. I have experience working with corporate tax for Wealth and Asset Mangement clients and since the beginning of my career in 2019, I noticed the heavy reliance of technology in my daily work. This exposure to different technologies sparked my curiosity for tech and thus the start of my software development journey began with the UT Austin Coding Boot Camp in January of 2021. For more of my work, check out my [Github profile](https://github.com/cliffybar) and [portfolio](https://cliffybar.github.io/Big-Red-Developer/)! 