# Matching an HTML Tag: RegEx Tutorial
Regular Expressions are a way of sifting through patterns of characters and matching them using literal and meta characters that identify patterns in a repeatable manner that, for example, would allow you to select/find all of the following:
* grey
* gray
* Gray
* Grey

Or perhaps you want to identify all the phone numbers, emails, urls, html tags, etc... You can do so with regular expressions!

This is an incredibly useful tool that can be used in many different ways, making it an extremely useful and versatile tool for developers to understand. 

## Summary
Let's break down how the following RegEx is able to match an html tag:
```
/^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/
```

This seemingly nonsensical string of characters is breaking down the exact criteria that must be met in order for a string of characters to be considered an HTML tag.
The first and final character, '/', represents the opening and closing of the regular expression.


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
* ``` / ``` : marks the opening and closing of the RegEx.
* ``` \ ``` : if followed by a single character, this component 'escapes' the character that might otherwise be a special character in a RegEx expression.
* ``` ^ ``` : the pattern immediately following ^ occurs at the beginning of a string
* ``` $ ``` : indicates that the specified pattern occurs at the end of a string
* ``` [] ``` : matches any single character within the specified range within the brackets... i.e. '[aeiou]' would match a single character with any vowel, and [^a-z] would translate to any character that is NOT in the alphabet (^ preceding the characters within the brackets operates much like ! in JavaScript)
* ``` | ``` : OR operator
* ``` () ``` : used to group expressions together
* ``` ? ``` : marks preceding character as OPTIONAL (i.e. ```colou?rs?``` could be color, colour, colors, or colours)
____
### Anchors
Let's look at our RegEx again: 
```
/^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/
```

The ```^``` as the second character is saying, "Hey! In order for this to be an HTML tag, the first character we see MUST be ```<```.

The ```$``` as the second to last character does something very similar only it tells us that the at the end of whatever string we are analyzing, the last thing will be ```>```.

________________
### Quantifiers
Quanitifiers such as ```*``` or ```{}``` describe the repetition of characters a certain amount of times. This particular RegEx isn't using too many quantifiers. Near the middle we can see ```>(.*)<```... the ```>``` would be the end of an opening HTML tag and the ```<``` is referring to the beginning character of an HTML closing tag (i.e. ```</div>```) and the ```(.*)``` between them is saying, any number (including 0) of any kind of character might be between the opening and closing HTML tags. Maybe a paragrage, or more HTML elements! This captures all of that.

At the second set of parentheses, ```([^<]+)``` , the ```+``` is the quantifier that refers to one or more of the preceding pattern or characters occuring. This particular part of the RegEx allows for attributes within the opening tag to be matched, stating one or more character that is not ```<``` will be matched.
 ___
### OR Operator
There is only one ```|``` (OR operator) in this expression. It is specifying that the preceding ```\/\1>``` OR the following ```\s+\/>``` would be matched.
___
### Character Classes
Identified by ```[]``` , character classes or character sets allow to create a pool of acceptable (or unacceptable) characters to match with. For example, ```[abc]``` translated to "any one character that is either a, b, or c.

So in our Regular Expression we are looking at, we can see near the beginning, ```([a-z]+)```. Inside the ```[]``` it's saying match any singular lowercase letter, however the ```+``` within the parentheses, but outside the square brackets, signifies that there must be at least ONE a-z character.
___
### Flags
```
 g , i , m , u , s , y 
 ```
 Flags are optional components of a regular expression that if added, modify how the expression searches for matches.
 Flags are denoted by a single lowercase letter.

 * ```i``` : ignores the 'casing' (uppercase v lowercase) of characters
 * ```g``` : causes the expression to seach for all occurances (global)
 * ```s``` : tells the 'wild character', ' ```.``` ' , match new lines as well
 * ```m``` : causes boundary characters ```^``` and ```$``` match the beginning and end of every single line, and not the entire string
* ```y``` : expression will start its search at the indicated index from its lastIndex property
* ```u``` : the expression will match 32-bit characters as well 


___
### Grouping and Capturing

___
### Bracket Expressions

___
### Greedy and Lazy Match

___
### Boundaries

___
### Back-references

___
### Look-ahead and Look-behind

___
## Author

Andy Bjerk is a full stack web developer. Find him on [GitHub](http://github.com/savoryboi)♡
