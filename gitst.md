# Regular Expression Tutorial

This tutorial is meant to be a foundational reference guide for anyone learning Regular Espressions.
By the end of this tutorial you will know what a Regular Expression (regex) is, when to use them, all of their different functionality, as well as some cool tips on how to improve your own regex scripting.

## Summary

In this tutorial we will discuss

Bonus: You can click <span><a href="https://regexr.com/" target="_blank">here</a></span> to navitage to an online regex editor so you can practice your regex scripting as you learn!

## Table of Contents

- [Regular Expression Tutorial](#regular-expression-tutorial)
  - [Summary](#summary)
  - [Table of Contents](#table-of-contents)
  - [Regex Components](#regex-components)
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
  - [About the Author](#about-the-author)

## Regex Components

### Anchors

<!-- Anchors are used for matching characters at the beginning and end of a string or adjacent to a word boundary. When using anchors, it's important to think about where the characters are located inside of the any given word or string before writing the expression. Placing the anchor before or after the string you're searching for in the expression will render differing results as seen in the example below. -->

Anchors are used for matching characters or a phrase at the beginning and end of a string. The `^` "carrot" and `$` "dollar-sign" anchors reference the begining and end of a line. RegEx recognizes the end of a line as a series of characters that is terminated by a return.

- Example String:
  > “I wanted to eat, so I ate a cheeseburger at McDonald's.”

Let's say we wanted to find a match for any character located at the begining and end from our example string. In regex, the `.` "period" simply means any possible character.

`^.` matches
![Start (single line)](https://user-images.githubusercontent.com/87861603/143735449-e50525b3-b05b-430d-968d-60ace53dd30b.png)

`.$` matches
![end (single line)](https://user-images.githubusercontent.com/87861603/143735469-2f10f7f3-f31f-4de0-a210-18cb8ec87213.png)

### Quantifiers

Quantifiers are uesd when you want to find a match for a certain number of characters.

- All RegEx Quantifiers:

  - `*` 0 or More
  - `+` 1 or More
  - `?` 0 or One
  - `{5}` Exact Number
  - `{5,6}` Min and Max range of numbers

### OR Operator

The OR operator is used to find a match for one \_\_ or another. The OR operator is invoked with the `|` "pipe" character.

- Example String: <br>
  > “I like chocolate icecream. I like vanila icecream.”

If we wanted to match the whole string in the example above, we could
do so with the following expression:

`/i enjoy (chocolate|vanila) icecream./g`

### Character Classes

Character classes are used to find matches of a specific character set ane are invoked by the `[]` brackets. You can also join multiple character sets together by simply adding the next set imediatly after the previous set.

For example, if we wanted to find all lower-case alpha characters, we could do so with the following expression:

`/[a-z]/g`

If we wanted to find lower-case alpha characters, upper-case alpha characters, and numeric characters, we could do so with the following expression:

`/[a-zA-Z0-9]/g`

### Flags

Flags in Regex are placed at the end of an expression and they define different criteria for the searching behavior.

- All RegEx Anchors:

  - `/g` Global
    <br>
    The Global flag returns all matches in the entire file instead of only returning the first instance of the match.
    <br><br>

  - `/i` Case Insensitive
    <br>
    The Case Insensitive flag returns matches regardless of upper or lowercase alpha characters.
    <br><br>

  - `/m` Multiline
    <br>
    The Multiline flag is used in conjunction with the `^` and `$` anchors.
    By default, the `^` and `$` anchors will only return a result if there is a match in the first line.
    When the `/m` flag is added however, the expression will search ALL lines of code for a match.
    <br><br>

  - `/s` Single Line
    <br>
    The Single Line flag returns matches
    <br><br>

  - `/u` Unicode
    <br>
    The Unicode flag returns matches
    <br><br>

  - `/y` Sticky
    <br>
    The Sticky flag returns matches
    <br><br>

### Grouping and Capturing

Grouping is useful if we want to find a specific character or phrase within another phrase we're searching for. Groups are invoked with the `()` parentheses.

- Example String:
  > Peter piper picked a patch of pickled peppers

For example, if we wrote `/p(i|e|a)/g` as our expression, we would match:
<img width="436" alt="Screen Shot 2021-11-29 at 10 05 29 AM" src="https://user-images.githubusercontent.com/87861603/143902327-c5d6164b-d1d9-449b-bd4a-aeed2b37fb3b.png">

### Bracket Expressions

Bracket expressions are very similar to character classes in that they are invoked by the same `[]` brackets except they are primarily used for matching specific special characters.

For example, the regex `[.[{()\\+*\]^$|?]` would match

### Greedy and Lazy Match

### Boundaries

Boundaries or "word boundaries" are used when we want to match one or more characters of a word but only if it's located at the begining or the end of the word.

<!-- Boundaries are similar to anchors in how they search for matches except that anchors search for matches in the scope of an entire strings, wherease boundaries search for matches in the scope of a single word. -->

- RegEx boundaries:
  - `\b` Word Boundary
  - `\B` Not a Word Boundary

The `\b` and `\B` boundaries reference "word boundaries" which are found at the begining or end of a word. <br>

- Example String: <br>
  > “I wanted to eat, so I ate a cheeseburger at McDonald’s”

Let's say we wanted to find a match for "at" inside of our example string. Depending on where we place the anchor in our expression, we can match different instances of the string we're searching.

`at\b` matches
![at b](https://user-images.githubusercontent.com/87861603/143668111-d09e9dab-8c8b-446e-9d92-3a1015aca6b8.png)

`\bat` matches
![bat](https://user-images.githubusercontent.com/87861603/143668121-9b15c968-0e47-4d39-b2d2-8e6241c497d6.png)

`\Bat` matches
![Bat copy](https://user-images.githubusercontent.com/87861603/143668632-343e0bf7-2e93-44b8-90fb-851a1e4a7d8f.png)

`at\B` matches
![at B copy](https://user-images.githubusercontent.com/87861603/143668637-94b003c6-e649-4f62-9db6-a39c3da139e1.png)

### Back-references

### Look-ahead and Look-behind

## About the Author

Clayton Miller is a budding coder and web-developer. He started his journey in the world of coding at with the Full-Stack Web Development Bootcamp at the University of Texas. Clayton looks forward to learning more about all asects of web development, sharpening his coding skills and meeting more awesome coders who are just as excited about coding as he is!

- [Clayton Miller's GitHub](https://github.com/fremen432)
