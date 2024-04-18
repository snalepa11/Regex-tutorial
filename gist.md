# Regular Expression: Matching an Email

A regular expression, also known as a regex, is a pattern that describes a set of strings. Regular expressions are commonly used in programming to search for, match, and manipulate text.

In the context of email validation, a regular expression can be used to check whether an email address is properly formatted. By defining a pattern that matches valid email addresses, we can use a regular expression to quickly and efficiently validate user input.

## Summary

This tutorial will be explaing components of a regular expression used to match emails. This regex is depicted below:

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

This tutorial will touch on all components of this regex starting with Anchors and moving on to Flags and Character escapes. This comprehensive oveview of the email search regex will provide a foundation for a fundamental understanding of all other regualar expressions you may encounter. 

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
The components in this regular expression are as follows: 
* Anchors: `^` , `$`
* Quantifiers: `+` , `{x,y}`
* Grouping Constructs `()`
* Bracket Expressions `[]`
* Character Classes `a-z` , `0-9` , `-`
* The OR Operator `|`
* Flags 
* Character Escapes `\d` , `\.`


### Anchors
Anchors are characters that indicate the start or end of a line or string. 
The `^` character indicates the beginning of a string or line. 
The `$` character indicated the end of a string or line. 

### Quantifiers
Quantifiers in regular expressions (regex) are symbols or characters that specify the quantity or repetition of the preceding element in the pattern. They allow you to define how many times a character, group, or character class should appear in the input text to form a match.

In this regex we see the `+` and `{2,6}` quantifiers 

The `+` matches one or more of the preceding element. In the case of this regex, we see that the `+` matches one or more occurrences  of the character class `[a-z0-9_\.-]` This ensires that the local part of the email address contains at least one character and may contain more. The `+` is also used for the domain of the email address ensuring that it contains at least one character and may contain more. 

The `{2,6}` matches at least 2 occurences of the preceding element and at most 6 of the character class `[a-z\.]`. This is commonly used to match TLDs such as .com, .org, .net, etc.


### Grouping Constructs
Grouping constructs in regular expressions are used to group multiple tokens together and treat them as a single unit. They serve several purposes, including defining the scope of alternation, applying quantifiers to multiple characters, and capturing substrings for later use or referencing.

In this regular expression, we see the grouping cpnstruct `()`. Parenthases are a basic and common grouping construct used to group enclosed token together. This creates an understadning of separation between strings in a regex. 

### Bracket Expressions
In this expression, we see the use of square brackets `[]` 
These brackets are used to signify a group of or range of characters that could be used in the input string. 
For example, this particular expression has the ranges of a-z and 0-9 inside of several brackets. This indicates that the user is allowed to use any characters form a-z and 0-9. 
### Character Classes
Character classes in regular expressions are used to match a single character out of a set of characters. They allow you to specify a range or a list of characters that you want to match. They are tied into bracket expressions as square brackets group characters together while character classes specify which characters are allowed within that specific group. For example, in this expression we see several bracket expressions and character classes: 
`[a-z0-9_\.-]`
`[\da-z\.-]`
`[a-z\.]`

These bracket expressions containt he character classes of a-z, 0-9, and hyphens (-)

### The OR Operator
Although there are no OR Operators in this regex. It can be helpful to touch on the purpose of the OR Operator. The OR Operator is identified by the `|` symbol. It is effectively another way of saying "or". for example cat|dog is equal to cat or dog. 
### Flags
This particular regex does not include any flags. However, it may be helpful to give the broad definition of a flag. 

Flags, also known as modifiers or options, are additional parameters that can be applied to a regular expression to change its behavior. These flags affect how the regular expression engine interprets the pattern and how it performs matching. Flags are typically appended to the end of the regular expression pattern, separated by slashes or other delimiters depending on the programming language or regex engine being used. They allow you to customize the behavior of your regular expressions to suit your specific matching requirements. Different programming languages and regex implementations may support different sets of flags, but some common ones include:

Case Insensitive (i):
This flag makes the regular expression case-insensitive, allowing it to match both uppercase and lowercase letters interchangeably.
Global (g):
This flag enables global matching, meaning that the regular expression engine will find all matches within the input string rather than stopping after the first match.
Multiline (m):
This flag changes the behavior of the ^ and $ anchors to match the start and end of lines within the input string, rather than just the start and end of the entire string.
Single Line (s):
This flag changes the behavior of the dot (.) metacharacter to match any character, including newline characters (\n), whereas without the flag, the dot matches any character except newline.


### Character Escapes
Character escapes are sequences of characters that have a special meaning and are used to represent certain characters or character classes. They allow you to match characters that have a special significance in regular expressions, such as metacharacters or characters with special properties.

This regular expression contains two character escapes identifies as, `\.` and `\d`

The `\.` character escape is matched to a literal dot. 
The `\d` character escape repressents a numerical digit from 0-9. 

For example, in this regex, the bracket expression `[\da-z\.-]` allows for digits from 0-9, letters from a-z, literal dots "." and hyphens "-". 


## Author
Sarah Nalepa
GitHub: https://github.com/snalepa11/Regex-tutorial

