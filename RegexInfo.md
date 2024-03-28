# Email RegEx Tutorial
This tutorial was made as a simple tutorial to explain the basics of RegEx (Regular Expressions) and how they work within java.

## Summary
In this tutorial we will be going over the RegEx for matching an email. The email regex is below.

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

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
Regex is a literal pattern of what it is you're looking for. A Regex has to have slashes at the beginning and end. The Regex for matching an email again is 
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ .
The following are the components that make up a regular expression.

### Anchors
The ^ and $ are both Anchors in regex with the ^ always being at the beginning and the $ always being at the end. This is because the ^ tells you that the string will begin with the characters after it. Just as the $ is the opposite and tells you that the string ends with the characters before it.

### Quantifiers
Quantifiers are the limits you need to set for matching individual parts or all of the string. examples of quantifiers in a string are as follows
*-Matches the pattern zero or more times,
+-Matches the pattern one or more times,
?-Matches the pattern zero or one time,
{ x }-Matches the pattern exactly x number of times,
{ x, }-Matches the pattern at least x number of times,
and
{ x, y }-Matches the pattern from a minimum of x number of times to a maximum of y number of times.

In our regex for an email we use the + twice and {2,6} once toward the end.
[a-z0-9_\.-]+ and [\da-z\.-]+ will both be looking for individual strings that match the pattern one time or more while,
[a-z\.]{2,6} will match any string in lowercase between 2 and 6 characters.

### OR Operator
The OR Operator is the | key on your keyboard it is used within grouping to make the expression work differently. In a later section on grouping we used the example (cat) which could only find "cat" in a string. But if you add the OR Operator like this (c|a|t) the expression can now find not only "cat" but also "act" ore even "atc". We do not use the OR Operator in our email regex.

### Character Classes
A Character Class is a defined set of characters which can be found within a string some of which I will go over in more detail in later sections of tutorial like bracket expressions. Other common examples of character classes are 
.—Matches any character except the newline character (\n),
\d—Matches any arabic numeral digit (this class is the same as using the bracket expression [0-9]),
\w—Matches any alphanumeric character from the basic Latin alphabet, including the underscore (this class is the same as using the bracket expression [A-Za-z0-9_]),
\s—Matches one whitespace character including tabs and line breaks.

\d, \w, and \s can also match the negative by capitalizing the letter for example: \D, \W, and \S.

### Flags
There is one exception to a regex being wrapped in slashes ( / ) and that exception is when you use Flag. A flag is used at the end of a regex after the second slash and they give you more detail on the functionality of the regex. The three most used flags are as follows,
g—for global search the regex will be tested against all possible matches in a string,
i—is for case-insensitive search the case of the characters should be ignored while attempting a match in a string,
m—is for a multi-line input string search and should be treated as multiple lines.

### Grouping and Capturing
A Grouping Construct is a way to break up the different sections in your regex using parentheses ( () ). These look for an exact match, so for example if you were to make one subexpression (cat) the only thing it could find is "cat" it could not find "act" or "candle". While Capturing is a way to treat a part of your pattern as a single unit. This can bve used to apply quantifiers or modifiers to several characters or patterns.
In our email regex we could split up the sections like this ([a-z0-9_\.-]+), ([\da-z\.-]+), ([a-z\.]{2,6}).

### Bracket Expressions
Bracket expressions are used with the square brackets ([]) to represent a range of characters we want to match. They can give you any length and just have to include one of the characters to match. example: [abc] could match you with "aaa", "cat" "cbaabc", "action", or "bananas". You could also use a hyphon for bracket expressions so instead of typing every letter of the alphabet inside square brackets we could just type [a-z]. We also have to remember that regex is case sensitive so the example would not be able to match with something like "ABC" or "CAT" for uppercase we could just do the same thing but uppercase like [ABC] or [A-C]. Other examples of bracket expressions would be [0-9] which can match you with a sting that can contain any number between 0-9, or [_-] which will match you with any string that has an underscore or hyphen in it. you can also put more than one in each bracket and example of this would be [a-zA-Z] which would give you any string that has any letters uppercase or lowercase.

heres a small recap of all the bracket expressions I mentioned in this portion
[a-z],
[A-Z],
[0-9],
[_-]

you can also add a ^ at the beginning to look for negatives. example: [^abc] this bracket expression will look for strings that do not include the lowercase letters a, b, or c.

In our regex for an email we have three bracket expressions which are [a-z0-9_\.-], [\da-z\.-], and [a-z\.]. 

### Greedy and Lazy Match
Very simply put a Greedy Match tries to match with a string as many times as it possibly can while a Lazy Match is the opposite and tries to match with a string as few times as it possibly can. 

### Boundaries
Boundaries are simply the positions between characters in a regex. For this example i'll use the | as a way to mark a boundary. example: |A| |d|o|g|. There is also such a thing as word boundaries where the boundary is around a specific word in a string. Using the same example as before (A dog) with the word "dog" being the specific word boundary we deem the boundaries would be placed like this instead. |A| |dog|.
A normal and word boundary are both represented by the special characters \b and \B, respectfully.

### Back-references
A Back-reference in regex is simply a way to match text that has already been matched using a capturing group. These capturing groups start at one and are preceeded with a slash, they also go in in value every time you use them. example: \1, \2, \3, \4, etc.

### Look-ahead and Look-behind
A Look-ahead and Look-behind assertions literally look ahead and behind where they are placed (to the right for look ahead and left for look behind). A look ahead assertion tries to match the next input with with a given pattern while a look behind assertion moves backwards and tries to match the previous input with with the given pattern.
The Look-ahead characters are (?=pattern) and (?!pattern),
and Look-behind characters are (?<=pattern) and (?<!pattern)

## Author
This tutorial was created by Dom Simonetta. Thank you for using it and I hope it helped you!

Link to my github- https://github.com/DomSimonetta
