# Regular Expression Tutorial

This tutorial is meant to be a foundational reference guide for anyone learning Regular Espressions.
By the end of this tutorial you will know what a regular expression is, when to use them, all of their different functionality, as well as some cool tips on how to improve your own regex scripting. Throughout this tutorial we'll be referencing a specific regular expression, breaking down each component and learning about the functionality of each part. 

Bonus: You can click <span><a href="https://regexr.com/" target="_blank">here</a></span> to navitage to an online regex editor so you can practice your regex scripting as you learn!

## Summary

Regular expression for email: `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

The goal of each regex is to return a match for a continuous series of characters. The type of characters, number characters and order of characters can all be specified and modified in the regex. 
The regex we'll be referencing in this tutorial searches for an email address such as "bob@gmail.com" and return a match if the structure of that email matches the criteria of our regular expression. 


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
      - [Positive Look-behind](#positive-look-behind)
      - [Negative Look-behind](#negative-look-behind)
      - [Positive Look-ahead](#positive-look-ahead)
      - [Negative Look-ahead](#negative-look-ahead)
  - [About the Author](#about-the-author)

## Regex Components

<br><br>

### Anchors
<br>

- Description: <br>
  > Anchors are used for matching characters or a phrase at the beginning and end of a string. RegEx recognizes the end of a string as a series of characters that is terminated by a return.
 

- Syntax: The `^` "carrot" references the begining of a line and `$` "dollar-sign" references the end of a line.

- Example:
  ```
  I wanted to eat, so I ate a cheeseburger at McDonald's
  ```

- Demo:
  > Let's say we wanted to find a match for any character located at the begining and end from our example string. In regex, the `.` "period" simply means any possible character.

  Regex: `^.`

  Match: <br>
  > ![Start (single line)](https://user-images.githubusercontent.com/87861603/143735449-e50525b3-b05b-430d-968d-60ace53dd30b.png)
  
  Explaination: <br>
  > The regex `^.` is basically saying, "Find an instance of any character `.` located at the begining of a string `^`."

  <br>

  Regex: `.$`

  Match: <br>
  > ![end (single line)](https://user-images.githubusercontent.com/87861603/143735469-2f10f7f3-f31f-4de0-a210-18cb8ec87213.png)
  
  Explaination: <br>
  > The regex `.$` is basically saying, "Find an instance of any character `.` located at the end of a string `$`."

<br><br>

### Quantifiers
<br>

- Description: <br>
  > Quantifiers are uesd when you want to return a match for a certain number of characters.

  <br>

- All RegEx Quantifiers:
  - `*` 0 or More
  - `+` 1 or More
  - `?` 0 or One
  - `{5}` Exact Number
  - `{5,6}` Min and Max range of numbers

  <br>

- Example:
  ```
  I am very veryy veryyy veryyyy hungry
  ```

  <br>

- Demo:
  > Lorem

  Regex: `very *`

  Match: <br>
  ![*](https://user-images.githubusercontent.com/87861603/144788009-0d86371b-b88e-4274-9b8d-314ae096892b.png)
  
  Explaination: <br>
  > The regex `very *` is basically saying, "Find all instances of 'very' that are followed by 0 or more " " space characters."

  <br>

  Regex: `very +`

  Match: <br>
  ![+](https://user-images.githubusercontent.com/87861603/144787988-2ab92b5d-cbcb-42b3-ace6-1812f70aa4f5.png)
  
  Explaination: <br>
  > The regex `very +` is basically saying, "Find all instances of 'very' that are followed by one or more " " space characters."

  <br>

  Regex: `very?`

  Match: <br>
  ![?](https://user-images.githubusercontent.com/87861603/144788034-500446ad-a2d5-4ca8-bcc9-03bf2901eec4.png)
  
  Explaination: <br>
  > The regex `very?` is basically saying, "Find all instances of 'ver' that are followed by 0 or 1 "y" characters."

  <br>

  Regex: `very{3}`

  Match: <br>
  ![{3}](https://user-images.githubusercontent.com/87861603/144788073-a1ee954f-2a81-4391-92b7-4924d4a46ddd.png)
  
  Explaination: <br>
  > The regex `very{3}` is basically saying, "Find all instances of 'ver' that are followed by exactly 3 "y" characters."

  <br>

  Regex: `very{2,4}`

  Match: <br>
  ![{2,4}](https://user-images.githubusercontent.com/87861603/144788880-71e7960a-e8c0-4539-8b24-088681149f7e.png)

  
  Explaination: <br>
  > The regex `very{2,4}` is basically saying, "Find all instances of 'ver' that are followed by 2-4 "y" characters."

<br><br>

### OR Operator
<br>
The OR operator is used to find a match for one \_\_ or another. The OR operator is invoked with the `|` "pipe" character.
<br><br>


- Example String: <br>
  > “I like chocolate icecream. I like vanila icecream.”

If we wanted to match the whole string in the example above, we could
do so with the following expression:

`/i enjoy (chocolate|vanila) icecream./g`

<br><br>

### Character Classes
<br>
Character classes are used to find matches of a specific character set ane are invoked by the `[]` brackets. You can also join multiple character sets together by simply adding the next set imediatly after the previous set.
<br><br>
For example, if we wanted to find all lower-case alpha characters, we could do so with the following expression:

`/[a-z]/g`

If we wanted to find lower-case alpha characters, upper-case alpha characters, and numeric characters, we could do so with the following expression:

`/[a-zA-Z0-9]/g`

<br><br>

### Flags
<br>
Flags in Regex are placed at the end of an expression and they define different criteria for the searching behavior.
<br><br>
- All RegEx Flags:

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

<br><br>

### Grouping and Capturing
<br>
Grouping is useful if we want to find a specific character or phrase within another phrase we're searching for. Groups are invoked with the `()` parentheses.
<br><br>
- Example String:
  > Peter piper picked a patch of pickled peppers

For example, if we wrote `/p(i|e|a)/g` as our expression, we would match:
<img width="436" alt="Screen Shot 2021-11-29 at 10 05 29 AM" src="https://user-images.githubusercontent.com/87861603/143902327-c5d6164b-d1d9-449b-bd4a-aeed2b37fb3b.png">

<br><br>

### Bracket Expressions
<br>
Bracket expressions are very similar to character classes in that they are invoked by the same `[]` brackets except they are primarily used for matching specific special characters.
<br><br>
For example, the regex `[.[{()\\+*\]^$|?]` would match

<br><br>

### Greedy and Lazy Match
<br>

- Description: <br>
  > Lorem 

- Syntax: Lorem

- Example:
  ```
  Lorem
  ```

- Demo:
  > Lorem


<br><br>

### Boundaries
<br>

- Description: <br>
  > Boundaries or "word boundaries" are used when we want to match one or more characters of a word but only if it's located at the begining or the end of the word. 

- Syntax: `\b` references a word boundary and `\B` references a non-word boundary.

- Example:
  ```
  I wanted to eat, so I ate a cheeseburger at McDonald’s
  ```

- Demo:
  > Let's say we wanted to find a match for "at" inside of our example string. Depending on where we place the anchor in our expression, we can match different instances of the string we're searching.

  <br>
  
  Regex: `at\b`

  Match: <br>
![at b](https://user-images.githubusercontent.com/87861603/143668111-d09e9dab-8c8b-446e-9d92-3a1015aca6b8.png)
  
  Explaination: <br>
  > The regex `at\b` is basically saying, "Find all instances of 'at' that are followed by a word boundary."

  <br>

  Regex: `at\B`

  Match: <br>
![at B copy](https://user-images.githubusercontent.com/87861603/143668637-94b003c6-e649-4f62-9db6-a39c3da139e1.png)

  Explaination: <br>
  > The regex `at\B` is basically saying, "Find all instances of 'at' that are NOT followed by a word boundary."

  <br>

  Regex: `\bat`

  Match: <br>
![bat](https://user-images.githubusercontent.com/87861603/143668121-9b15c968-0e47-4d39-b2d2-8e6241c497d6.png)

  Explaination: <br>
  > The regex `\bat` is basically saying, "Find all instances of 'at' that are preceded by a word boundary."

  <br>
  
  Regex: `\Bat`

  Match:  
  ![Bat copy](https://user-images.githubusercontent.com/87861603/143668632-343e0bf7-2e93-44b8-90fb-851a1e4a7d8f.png)

  Explaination: <br>
  > The regex `\Bat` is basically saying, "Find all instances of 'at' that are NOT preceded by a word boundary."
  

<br><br>

### Back-references
<br>

- Description: <br>
  > Back-references are used to search for multiple instances of some criteria inside a single string. Back-refernces are invoked with `\1` 

- Syntax: `(criteria-1)\1` 

- Example:
  ```
  We the People of the the United States, in Order to form a more more perfect Union, establish Justice, insure domestic Tranquility, provide for the the common defence, promote the general Welfare, and and secure the Blessings of Liberty to ourselves and our Posterity, do do ordain and establish this Constitution for the United States of of America.
  ```

- Demo: 
  > Lets say we wanted to find all instances of repreated words in our example. We can use back-referencing to do this.

  Regex: `\b(\w+)\s\1\b`

  Match: <br>
  > ![back-reference](https://user-images.githubusercontent.com/87861603/144773424-320b4fd7-e560-4770-80a7-1fa275a3d110.png)

  Explaination: <br>
  > Our regex is basically saying, "Find all instances of a word `\w` of any length `+` followed by a space `\s` that repeats `\1`. These repeating words must also be inside a word boundary `\b`."

<br><br>

### Look-ahead and Look-behind
<br>

- Description: <br>
  > Look-ahead and Look-behind, collectively called “lookaround”, searches for a set of 2 criteria in sequence and returns a match for whatever is in "ahead" or "behind" it depending on the criteria specified in the regex.

<br>

- Look-around example:

  ```
  https://www.google.com
  http://www.google.com
  https://www.facebook.com
  http://www.facebook.com
  ```

<br>

#### Positive Look-behind

<br>

- Description: <br>
  > Positive Look-behind searches for 2 criteria in sequence and returns a match for the second criteria, but only if the first criteria is "behind" it.

- Syntax: `(?<=(criteria-1))(criteria-2)`

- Demo:
  > Let's say we wanted to write a regex using Positive Look-behind that returns all matches for "google.com" so long as it has "https://www." behind it. We could do this with the following:
  
  Regex: `(?<=(https:\/\/www.))(google.com)`

  Match: <br>
  > ![Look-behind positive](https://user-images.githubusercontent.com/87861603/144766356-0b8a6947-97ce-43a1-8c59-e92b3d6f3d0d.png)
  
  Explaination: <br>
  > This expression is basically saying, "Return and match 'google.com' but only if 'https://www.' is behind it." Notice the "google.com" on line 2 is not matched because the string behind it, "http://www.", doesn't match criteria-1 in our regex.

<br>

#### Negative Look-behind

<br>

- Description: <br>
  > Negative Look-behind searches the exact same way as Positive Look-behind except it matches and returns the inverse.

- Syntax: `(?<!(criteria-1))(criteria-2)`

- Demo:
  > If we use the same example as above except we change our regex to have a Negative Look-behind syntax, `(?<=(https:\/\/www.))(google.com)`, it will match and return all instances of "google.com" that do NOT have "https://www." behind it.

  Regex: `(?<!(https:\/\/www.))(google.com)`

  Match: <br>
  > ![Look-behind negative](https://user-images.githubusercontent.com/87861603/144766381-bfe0ce08-5db7-4e42-801d-b214bc9d7038.png)

  Explaination: <br>
  > This expression will only return the "google.com" on line 2 becasue that's the only instance of "google.com" in our example where "https://www." is not behind it.

<br>

#### Positive Look-ahead

<br>

- Description: <br>
  > Positive Look-ahead searches for 2 criteria in sequence and returns a match for the first criteria but only if the second criteria is ahead of it.

- Syntax: `(criteria-1)(?=(criteria-2))`

- Demo:
  > Using our example, let's say we wnat to return all instances of "https://www." but only if "google.com" is ahead of it. We could do this with the following:

  Regex: `(https:\/\/www.)(?=(google.com))`

  Match: <br>
  > ![Look-ahead positive](https://user-images.githubusercontent.com/87861603/144766393-6fa9a579-ba5f-48fa-9088-f8a8c55f4048.png)

  Explaination: <br>
  > This expression will only return the "https://www." on line 1 becuase that's the only instance in our example where "google.com" is ahead of it.

<br>

#### Negative Look-ahead

<br>
 
- Description: <br>
  > Just like how Negative Look-behind searches the inverse of Positive Look-behind, Negative Look-ahead searches the exact same way as Positive Look-ahead but matches and returns the inverse. Negative Look-ahead searches for 2 criteria in sequence and returns a match for the first criteria EXCEPT if the second criteria is ahead of it.

- Syntax: `(criteria-1)(?!(criteria-2))`

- Demo:

  Regex: `(https:\/\/www.)(?!(google.com))`

  Match: <br>
  > ![Look-ahead negative](https://user-images.githubusercontent.com/87861603/144766400-4b2ec580-fc56-45a9-b515-1b807c22ec2a.png)

  Explaination: <br>
  > This expression will only return the "https://www." on line 3 because that is the only instance of "https://www." in our example where "google.com" is NOT ahead of it.

<br><br>

## About the Author

<br>

Clayton Miller is a budding coder and web-developer. He started his journey in the world of coding at with the Full-Stack Web Development Bootcamp at the University of Texas. Clayton looks forward to learning more about all asects of web development, sharpening his coding skills and meeting more awesome coders who are just as excited about coding as he is!

- [Clayton Miller's GitHub](https://github.com/fremen432)

- [claytonmiller.tech](http://www.claytonmiller.tech/)
