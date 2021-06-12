# Regex Tutorial

Writing properly working code cannot be done without first understand how the code itself functions. By understanding why a code is written in its unique sequence, a developer will be better equipped when tasked to explain theirs or others' code.

## Summary

Regular expressions, also known as regex, are a sequence of characters that define a specific search pattern. When included in code or search algorithms, a regex can be used to find certain patterns of characters within a string, or to find and replace a character or sequence of characters within a string.

In my regex tutorial, I will be describing matching an email:

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

## Table of Contents

- [Overview](#overview)
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

### Overview

An example for an email regex is as follows: `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

To make this example more user-friendly, think of it in three groups:

1. Username: `/^([a-z0-9_\.-]+)@`
    
    A username can accept values ranging from letters between a-z, numbers between 0-9, the underscore _ character, the period . character, and the hyphen - character. An example would be `clifford_crowell@emaildomain.extension`, `or clifford.crowell@emaildomain.extension`.

2. Email domain: `([\da-z\.-]+)\.`
    
    An email domain can accept values ranging from a single digit between 0-9, letters between a-z, the period . character, and the hyphen - character. An example would be `username@10gmail.extension`. 

3. Extension: `([a-z\.]{2,6})$/`
    
    An extension can accept values ranging from letters between a-z and the period . character, and cannot be less than 2 or more than 6 characters long. An example would be `username@emaildomain.com`.


### Anchors

1. `^` : Matches the beginning of the string, or the beginning of a line if the multiline flag (m) is enabled. This matches a position, not a character.

2. `$` : Matches the end of the string, or the end of a line if the multiline flag (m) is enabled. This matches a position, not a character.


### Quantifiers

1. `+` : Matches 1 or more of the preceding token.


### OR Operator



### Character Classes

1. `\d` : Matches any single digit character (0-9). Equivalent to [0-9].

    Ex. Think of the text string `ab2 ab34 ab5 ab67`. The character class `\d` will match `2`, `3`, `4`, `5`, `6`, and `7` all as individual digits despite `34` and `67` being one right after the other.


### Flags



### Grouping and Capturing

1. `()` : Groups multiple tokens together and creates a capture group for extracting a substring or using a backreference.
    
    Ex. Username group is `([a-z0-9_\.-]+)`, email domain group is `([\da-z\.-]+)`, and extension group is `([a-z\.]{2,6})`. 


### Bracket Expressions

1. `[]` : Match any character in the set.

    Ex. `[a-z]` and `[0-9]` in the Username group means that the username may allow characters between letters a through z and numbers between 0 through 9 to be included in the username. 


### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
