# Regular Expression Tutorial

This tutorial is meant to be a foundational reference guide for anyone learning Regular Espressions.
By the end of this tutorial you will know what a Regular Expression (regex) is, when to use them, all of their different functionality, as well as some cool tips on how to improve your own regex scripting.

## Summary

In this tutorial we will discuss 

Bonus: You can click <span><a href="https://regexr.com/" target="_blank">here</a></span> to navitage to an online regex editor so you can practice your regex scripting as you learn!

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

## Regex Components

### Anchors   

Anchors are used for matching characters at the beginning and end of a string or adjacent to a word boundary. When using anchors, it's important to think about where the characters are located inside of the any given word or string before writing the expression. Placing the anchor before or after the string you're searching for in the expression will render differing results as seen in the example below. 

- All RegEx Anchors:

``\b`` Word Boundary          <br>
``\B`` Not a Word Boundary    <br>
``^``  Beginning of a String  <br>
``$``  End of a String        <br>


<br>

The ``\b`` and ``\B`` anchors reference "word boundaries" which are found at the begining or end of a word. <br>

- Example 1: <br> ``“I wanted to eat, so I ate a cheeseburger at McDonald’s”``

Let's say we wanted to find a match for "at" inside of Example 1. Depending on where we place the anchor in our expression, we can match different instances of the string we're searching.

``at\b`` matches
![at b](https://user-images.githubusercontent.com/87861603/143668111-d09e9dab-8c8b-446e-9d92-3a1015aca6b8.png)

``\bat`` matches
![bat](https://user-images.githubusercontent.com/87861603/143668121-9b15c968-0e47-4d39-b2d2-8e6241c497d6.png)

``\Bat`` matches
![Bat copy](https://user-images.githubusercontent.com/87861603/143668632-343e0bf7-2e93-44b8-90fb-851a1e4a7d8f.png)

``at\B`` matches
![at B copy](https://user-images.githubusercontent.com/87861603/143668637-94b003c6-e649-4f62-9db6-a39c3da139e1.png)

<br>

The ``^`` and ``$`` anchors reference the begining and end of a string. RegEx recognizes the end of a string as a series of characters that is terminated by a return.

- Example 2: <br> ``I wanted to eat, so I ate a cheeseburger at McDonald’s. Then I went to my car to drive home.`` <br>
``Once I got home I realized I was still hungry, so I returned to McDonalds for another delicious cheeseburger.``

Let's say we wanted to find a match for any character located at the begining and end of each string in Example 2.

``^.`` matches
![start](https://user-images.githubusercontent.com/87861603/143669695-dc055880-de23-41c3-91db-2519f23b76dd.png)

``.$`` matches
![end](https://user-images.githubusercontent.com/87861603/143669664-034ae01a-a819-4d4d-b42f-d530d59057ef.png)

### Quantifiers

### OR Operator

### Character Classes

### Flags

- All RegEx Anchors:

``/g`` Global          <br>
``/i`` Case Insensitive    <br>
``/m``  Multiline  <br>
``/s``  Single Line        <br>
``/u``  Unicode        <br>
``/y``  Sticky        <br>

### Grouping and Capturing

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## About the Author

Clayton Miller is a budding coder and web-developer. He started his journey in the world of coding at with the Full-Stack Web Development Bootcamp at the University of Texas. Clayton looks forward to learning more about all asects of web development, sharpening his coding skills and meeting more awesome coders who are just as excited about coding as he is!

- [Clayton Miller's GitHub](https://github.com/fremen432)
