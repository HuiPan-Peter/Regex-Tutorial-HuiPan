# [Regex: A Regular Expression Tutorial](https://gist.github.com/HuiPan-Peter/39c6ed15cabad0038b4098ef1e22eb92)

The purpose of this tutorial is to discuss regular expressions step by step, and discuss their possible uses. A regular expression, also known as regex, is a sequence of characters that defines a search pattern in text.

## Demo Regular Expression (A Sample Regex)

For example, regex can be used to match an email address by using the following expression:

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

This tutorial will break down each part of the preceding expression and describe what it does.

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
- [Summary of Demo Regex](#Summary-of-Demo-Regex)

## Regex Components

### [Anchors](#table-of-contents)

Anchors are used to match patterns at the beginning or end of a line, word, or string.

For example, the `^`, caret, identifies the beginning of the string, while `$` matches the end. In our example, we are looking for a character at the start that matches one of the following, listed after the `^`:

`/^([a-z0-9_\.-]+)`

and at least one of the following characters at the end, before the `$`.

`.([a-z\.]{2,6})$/`

### [Quantifiers](#table-of-contents)

Regex quantifiers define how many instances of a group, character, or character class must exist in the input to be considered a match.

Consider the quantifier `+` in our example:

`([a-z0-9_\.-]+)`

This indicates that to be a match, the string must have at least one of the following characters:

`a-z, 0-9, _, -, .`

### [OR Operator](#table-of-contents)

The logical OR `|` regex operator is used to match characters from either the left or right of the `|` operator. While the OR operator is not present in our given example, we can consider the following:

`/apple|orange/`

Here, the regex will match either "apple" or "orange".

### [Character Classes](#table-of-contents)

Regex character classes are a set of characters enclosed within square brackets. Here, the regex engine looks for only one out of several characters enclosed within the square brackets. For example, instead of our preceding `{gray, grey}` example, we could instead use `gr[ae]y` to match either word.

Consider this snippet from our matching email example:

`@([\da-z\.-]`

Here, our regex looks for at least a single letter character match from a-z after the @ symbol.

### [Flags](#table-of-contents)

While there are no flags present in our matching email regex, we can consider the 6 optional regex flags in JavaScript:

1. `i`
   - This flag is case insensitive. `ORANGE` and `orange` are the same.
2. `g`
   - Looks for all matches, rather than just the first.
3. `m`
   - multiline mode
4. `s`
   - dotall mode, in which `.` matches `\n`, or a newline.
5. `u`
   - enables unicode support.
6. `y`
   - searches the exact position in the text.

### [Grouping and Capturing](#table-of-contents)

Capturing groups allows us to match multiple characters as a single unit, or set of parenthesis.

In our matching email example we have three groups captured:

1. `([a-z0-9_\.-]+)`
2. `([\da-z\.-]+)`
3. `([a-z\.]{2,6})`

In these three groups, one of the characters in group 1 must be present before proceeding to group 2, and so on.

### [Bracket Expressions](#table-of-contents)

A regex bracket expression matches a specific set of single characters, or character class.

In our example,

`[a-z\.]`

We are looking for letters `a-z` rather than `a`, `-`, and `z`.

### [Greedy and Lazy Match](#table-of-contents)

In regex, greedy means to match the longest possible string, while the lazy match looks for the shortest possible string.
While not present in our matching email regex, we can consider: `<div>Hello World!</div>` in context of the following examples:

Greedy:
`<.+>`

Here, our regex will match all of `<div>Hello World!</div>` - from starting `<` to ending `>`.

Lazy:
`<.+?>`

Here, however, our regex repeats as few times as possible, so it will only match to the first ending `>` or `<div>`.

### [Boundaries](#table-of-contents)

Regex boundaries, `\b` matches a word boundary. This allows you to search for whole words only. While not present in our matching email regex, we can consider `\borange\b` in which our regex looks for the specific word `orange`.

### [Back-references](#table-of-contents)

Regex back-references match the same characters as matched before by a capturing group. We don't have any present in our matching email regex, but basically, this allows us to back reference the captures we've made previously.

### [Look-ahead and Look-behind](#table-of-contents)

Look-ahead and look-behind assertions are also known as lookarounds and only tell us whether a characters are a match or not. While not present in our matching emails regex, we can consider the following:

- Lookahead

`\d+(?=888)`

In this example, any found digits must have `888` after to be considered a match. So `128` is not a match, but `12888` is.

- Lookbehind
  - A lookbehind matches only if there's something before it:

`(?=88)+\d`

So `12` is not a match, but `8812` does.

### [Summary of Demo Regex](#table-of-contents)

Demo regular expressions: `^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$`

- ^ It is the start of the string.
- ([a-z0-9_\.-]+) Matching any letter a-z and is case senstive. It also matches a character 0-9 and matches the characters "\_" , "-" , and ".";
- @ The string should contains ‘@’ character after some alphanumeric characters.
- ([\da-z\.-]) Matching a single digit from 0-9, any character a-z (case senstive), and the characters "." and "-".;
- \. Email should contain a dot followed by ‘@’ and characters;
- ([a-z\.]{2,6}) Matching any character a-z(case senstive) and the character ".", and should contain from 2 to 6 alphabetical characters at the end of the string.
- $ The end of the string.

## Author

This tutorial was created by: <a href="https://github.com/HuiPan-Peter" target="_blank">Hui Pan</a>

If you have any question, could contact me by: <a href="mailto:guaranstone@gmail.com">Email</a>
