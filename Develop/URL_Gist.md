# Regex Tutorial for URL


Regular Expressions are used accross different coding languages and is not restricted to any one language. This gist will explain how you can use Regular expression to validate a URL within the Javascript language.


## Summary


Regular Expression  use both literal and metacharacters to process/identify text. It is used to pattern match. It's sort of like when you use the cmd+F search but instead of using litteral characters for the search you use a combination of literal and metacharchater for your search. I'm goin to go over the different parts of Reqular Expression and will define how to validate a URL using regulart expressions. Here is what we will be breaking down `/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/`


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
Anchors are defined with  ^ which is used for the beginning. In our example the carrot comes before (Https?:\/\/). We will talk about some of the other characters later but for now we are focused on the http. The anchor is saying that our search must start with http. The $ signifies the end.
### Quantifiers
There are several Quantifiers. The * means it is supposed to match 0 or more, + is to match 1 or more, ? matches 0-1, {n} matches the exact number, {n, } matches at least n times and{n,x} matches min and max times. In the example of the YRL we use Qualifiers in two spots: the second set of parentheses and the third. The second set would typically be the name of the website and the quantifier is saying that it has to have 1 or more characters.  The third set is defining the domain and that the min number of characters is 2 and the max is 6. And I almost forgot about the * which is used to represent 0 or more which means that after the domain you can but you don't have to use \ to continue the URL.


### OR Operator
The OR operator uses pipes but we are not going to go into too much detail since it is not used in the URL regex. But it allows you to make a subexpression not have to be an exact match.
### Character Classes
You use character classes to tell the regex engine to only match the defined characters. To do this you place it inside brackets. Let's define a couple \d represents 0-9, . represents any character, \w is capital A to Capital Z, lowercase a-z and also 0-9, whitespace is \s, non-whitespace \S, and any non-character is \W. In the first section it's defined that what we are looking for in the second set of parentheses test can match any given digit and then combined with the quantifier it can be any number of digits`[\da-z\.-]+`. In the third set of parentheses  it's saying that it can only be a-z for the characters `[a-z\.]{2,6}`. The fourth set also allows for any type of digit `[\/\w \.-]*`
### Flags
Flags are g- for global which is all possible matches in a string. For a case-insensitive search we have i. And the third flag is m which is for a multi-line search.  We however are not using any of these in our URL regex.
### Grouping and Capturing
We are using 4 capturing groups to define a URL they are each split up by using () Group 1 `(https?:\/\/)?`, Group 2 `([\da-z\.-]+)`, Group 3 `([a-z\.]{2,6})`and Group 4 `([\/\w \.-]*)*`.
### Bracket Expressions
Brackets are used in several places so we can break that down but first brackets represent a range of characters. Brackets by default are positive but can turn them to a negative by using the ^.This means that typically you are searching for the things inside the bracket however when you use the ^ inside before you enter your characters you are saying find a string that does not include those characters.  We did not use the negative in this example
### Greedy and Lazy Match
Greedy matches the longest string and lazy matches the shortest. In our URL example we use the greedy twice. In group 2 the + is one and unlimited. In group four the * is zero and unlimited.
### Boundaries
Boundaries are set by placing a word between \b and \b. We do not use this in our URL regex so there is not an example to provide.
### Back-references
with back-references you can refer back to a capturing group by using \1. This is not used for the URL example.
### Look-ahead and Look-behind
This gist was a great opportunity to learn a little about Regex/Regular Expression. I think I was able to get an understanding of what it is and the purpose but will definitely need to do more studying to really get a grasp on what is happening and how to use it in my coding.
## Author




 [GitHub](StamperM)