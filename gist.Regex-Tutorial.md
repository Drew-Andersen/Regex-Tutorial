# Regular Expression - Mathcing a URL

Regular expressions, often refered to as Regex, refers to a distinct sting usually made up of various sets of characters that can be used as both a query tool and a validator. Regex was derived in the early 1950's out of the concept of regular language coined by the mathemitician stephen Cole Kleene. Regex became widely used in the 1960's within the theoretical computer science field as a way to mathc patterns within text fields. Although regular expressions are known for being extremely cryptic looking. when they are broken down, one can see that they are not as complex as they appear to be.

## Summary

This tutorial will be covering the regex expression used for both matching and validating a URL:

`/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/`

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
The regex components that define this particular expression are anchors, quantifiers, meta escape characters, character classes, single character matches, grouping and capturing, and bracket expression. Regarding the example used for this ttutorial: `^` and `$` are the anchors that are used, `+` and `{2, 6}` are the quantifiers, `\d` and `\w` represent the meta escape characters used, `[\da-z\.-]`, `[a-z\.]` represent the character classes, `./`, `-` represent the single character matches used, `()` represents the way that this regex utilizes grouping and capturing, and `[]` delinated the bracket expression used.

### Anchors
Anchors within regex mark the begining and end points of the expressions. The `^` marks the begining of the expression and `$` marks the end of the expression.

### Quantifiers
Quantifiers are meta characters that modify the previous character in the regexand say hoq many of those do I want match in a row.

Quantifiers allow the specification of how many characters or character classes should be matched.
- The `+` sign matches one or more preceeding characters.
- The `{min, max}` create a specific numerical quantifier range.

### Grouping Constructs
So what is included between the two anchors. If we examine the expression, we can see that there are a number of components separated by parentheses `()`. Parentheses are used in regex to create a separate groups of interest. Within each of these groups, there is a regex that we may look at separately to see what is evaluated. These include:
- the initial `https` component: `(https?:\/\/)`
- the domain name (e.g. `www.google`, or `pets`): `([\da-z\.-]+)\.`
- the top level domain (`.com`, `.gov`, etc): `([a-z\.]{2,6})`
- the file path: `([\/\w \.-]*)*`

### Bracket Expressions
`[]` create a character or group range and represents a single character. In regards to the regex in this tutorial, the brackets are used to separate each character class. The character can be anything specified within the brackets.
An example: `[a-z\.]` is a character that can be matched with any lowercase letters from `a-z` and a period `.`.

### Character Classes
Character classes are the attribute in a regex that allow us to define a specific set of characters that can be used in a search pattern.

In our tutorial the character classes that are used are `[\da-z\.-]`, `[a-z\.]`, and `\w`.
`[\da-z\.-]`: `\d` can be used to match any didgit (0-9), `a-z` matches a single character in the range between a and z (case sensitize), `\.` matches the character '.', and `-` matches the character '-'.
`[a-z\.]`: `a-z` matches a single character in the range between a and z (case sensitize), `\.` matches the character '.'.
`([\/\w \.-]*)`: The expression is allowing any number of filepath characters that may follow an initial specified domain.

Other examples of single letter characters:
`\s`: matches and white space as a space or a tab.

### The OR Operator
There are no OR operators within the example in this tutorial, but in general OR operators are represented by tge pipe `|` abd specified under the regex type of altercation.

### Flags
Regex flags are used to modify an expressions behavior. There are only 6 of them in JavaScript: i: case-sensitivity, g: looks for all matches, m" multiline mode, s: enables "dotall" mode that allows a dot `.` to match a new line character `\n`, u: enables full Unicode support, and y: "sticky" mode.

### Character Escapes
Chatacter escapes are useful when you want to match a character that is not easily represented in its literal form. For example, you cannot use a line break in a regex literal, or you must use a character escape.

## Author

Drew Andersen is a full stack developer with a bachelor's degree in biology from Georgia Southern University. He currently resides in Atlanta, GA.

Have additional questions? Click the links below to reach Drew through his GitHub account.
[Github](https://github.com/Drew-Andersen)
