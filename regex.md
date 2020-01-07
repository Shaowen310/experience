# Regex

## Quantifier

|Regular Expression|	Description|
|---|---|
|* |Occurs zero or more times, is short for {0,}|
|+ |Occurs one or more times, is short for {1,}|
|? |Occurs no or one times, ? is short for {0,1}|
|{X} |Occurs X number of times, {} describes the order of the preceding liberal|
|{X,Y} |Occurs between X and Y times|
|\*? |? after a quantifier makes it a reluctant quantifier. It tries to find the smallest match. This makes the regular expression stop at the first match.|



## Meta characters

|Regular Expression|	Description|
|---|---|
|\d | Any digit, short for [0-9] |
|\D | A non-digit, short for [^0-9] |
|\s | A whitespace character, short for [ \t\n\x0b\r\f]|
|\S | A non-whitespace character, short for [^\s]|
|\w | A word character, short for [a-zA-Z_0-9]|
|\W | A non-word character [^\w]|
|\b | Matches a word boundary where a word character is [a-zA-Z0-9_]|

## Look around

|Lookaround  |    Name      |        What it Does                       |
|------------|--------------|-------------------------------------------|
|(?=foo)     |   Lookahead  | Asserts that what immediately FOLLOWS the current position in the string is foo|
|(?<=foo)    |   Lookbehind | Asserts that what immediately PRECEDES the current position in the string is foo|
|(?!foo)     |   Negative Lookahead  | Asserts that what immediately FOLLOWS the current position in the string is NOT foo|
|(?<!foo)    |   Negative Lookbehind  | Asserts that what immediately PRECEDES the current position in the string is NOT foo|

## References

1. [Regular expressions in Java - Tutorial](https://www.vogella.com/tutorials/JavaRegularExpressions/article.html)

1. [Stack Overflow: How to match, but not capture, part of a regex?](https://stackoverflow.com/questions/3926451/how-to-match-but-not-capture-part-of-a-regex)
