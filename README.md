# Title (Regex-Tutorial)

Regex, or regular expressions are literals made up of special characters that define the parameters of a search pattern.  There are many uses for this, with one listed below

## Summary
Here is a code snippet for searching for a password, and it's strength.
^(?=.*[A-Z].*[A-Z])(?=.*[!@#$&*])(?=.*[0-9].*[0-9])(?=.*[a-z].*[a-z].*[a-z]).{8}$

Please reference the below components for context on the different regex components

The ^ anchor indicates the first character, followed by parenthesis enclosing ?=.*[A-Z].*[A-Z] as a grouping construct.  A ? quantifier is used where it checks to see if .*[A-Z] exists, which is then repeated twice, which indicates it is looking for 2 instances of the bracket expression.  The . and * refer to searching any character, but the bracket expression [A-Z] clarifies any uppercase characters between A-Z.  Similar logic is used inside the other grouping constructs, where (?=.*[!@#$&*]) is loking for one instance of the special characters in the [], (?=.*[0-9].*[0-9]) is looking for 2 instances of numbers between 0-9, and (?=.*[a-z].*[a-z].*[a-z]) is looking for 3 instances of lowercase alphanumeric characters between a-z.  Finally, the {8} quantifier shows that the string must be 8 characters long, followed by the $ indicating that that is the end of the search criterion.


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
The regex components are the rules and tools of what the search parameter will look for in a string.

### Anchors
The characters that are represented as anchors in a regex, or regular expression are ^ and $.  
When looking at this representation, the ^ anchor says that a string begins with the character that follows the ^. You see this as the first character in the regex representation above in the summary section and in the line below.

^(?=.*[A-Z].*[A-Z])(?=.*[!@#$&*])(?=.*[0-9].*[0-9])(?=.*[a-z].*[a-z].*[a-z]).{8}$


  The other character, $, has the role of indicating that the character preceding $ is the last in the string being searched, and ends the string.\

### Quantifiers
Quantifiers set limiters that provide specifications such as how long the string search.  You can see several examples in this example

The symbol ? is one of the limiters referenced, that states that the following must match 0 or 1 time, which is stating that it searches all the [A-Z], [a-z], [!@#$&*], and [0-9] arrays.

The .* means it searches for one of any character, and is referenced twice for [A-Z], and [0-9] within the grouping construct(listed below), meaning that the string needs to have at least 2 uppercase, 2 lowercase, and 2 numerals.  Also, it only references [!@#$&*] once, so it only needs one of those special characters in the array.  It also references [a-z] 3 times, which means it needs at least 3 lower case letters

Additionally,the {} refers to the string needing to be 8 characters. The {} could be used in multiple ways, for example if it was written {8, }, it would mean at least 8 characters, or if it was written { 8, 16} it would mean 8 to 16 characters.

^(?=.*[A-Z].*[A-Z])(?=.*[!@#$&*])(?=.*[0-9].*[0-9])(?=.*[a-z].*[a-z].*[a-z]).{8}$

### Grouping Constructs
The grouping construct is used to isolate searching parameters through parenthesis, which makes a subexpression within.  You can see this occur here, where
(?=.*[A-Z].*[A-Z]),  (?=.*[!@#$&*]), (?=.*[0-9].*[0-9]), and (?=.*[a-z].*[a-z].*[a-z]) are all subexpressions of the expression

### Bracket Expressions
When in the brackets, it shows the range of characters that fit within the search criterion, however it does not relate to the search or the string.  You can see that they are defined as:
 [A-Z] the uppercase letter characters,
 [a-z] The lowercase letter characters,
 [0-9] The numeral characters, and
 [!@#$&*] The acceptible special characters for the password
### Character Classes

Character classes represent the different sets of characters used. 
/d represents numerals (digits)
/w represents letters and the _ underscore sign (words)
/s represents spacing characters, such as tab or single space

. is another character class, which is used in the example code above.  It can represent any character except for the newline /n, and clarifies that any character within the brackets can be used


### The OR Operator

The OR operator is not used in this code example, but is characterized by |.  When used within bracket such as [], it indicates the value OR the other, it can be used multiple times, indicating there are multiple passing conditions for the regex search

### Flags

Flags are used at the end of a regex in order to indicate additional functionality or limitations of the regex, such as:
i- match character, but does not matter if upper or lower case
g- global: check every possible match inside of a string
m- string separated by multiple lines should be treated as separate strings in regards to this search

### Character Escapes

Character escapes use backslashes \  to enclose the character in order to prevent the search from interpreting the code literally, and instead looks for it as a character, causing them to lose their significance inside the backslash.
For example, the \{\ would be enclosed, and not be an indicator something like the start of a quantifier, but instead whould eb searched for in the string.

## Author

Nick Lyle, Fullstack Bootcamp student
https://github.com/NickLyle2009
https://github.com/NickLyle2009/Regex-Tutorial