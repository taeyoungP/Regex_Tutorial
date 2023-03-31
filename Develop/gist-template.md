# Regex Tutorial (What is Regex?)

Regex or Regular Expressions is a sequence of characters that specifies a match pattern in text. Regex is helpful when user wants to apply filter to search and manipulate text used for programming languages and applications, such as finding/validating matching text/characters in email, hex value, URL tag, HTML tag, and etc. 

This Regex Tutorial is to explain how Regex works by breaking down each part of the expression.

## Summary

The contents of the tutrial will help anyone who wants to undesrtand to how to use them or who wants to use/create their own regex combination. 

In this tutorial, the following regular expression is being used for explanation:
    ```
        `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`
    ```

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
There are different components of Regex: Anchors, Qunatifiers, Grouping Constructs, Bracket Expressions, Character Classes, The OR Operator, Flags, and Character Escapes.

Before moving in on each of the components(writing pattern), Regex is constructed using a literal. Therefore, Regex pattern should be enclosed by two slashes:
    ```
        /example_pattern/
    ```

As these slashes are for literal, the string inside of slashes will be searched as it written.

So in our example regex, anything between two slashes will be used to idenitfy email syntax or pattern.

### Anchors

There are anchors used in this regex. 
```
    '^' and '$'.
```

The first anchor, '^' indicates that the first string must be the opening string.

For example, if we use '^' anchor as following:

```
    /^hello/
```

This would look for string that starts with its exact same string 'hello'. 
```
    hello world
```
but the string does not contain 'hello' in the beginning will be not counted.
```
    world hello
```

When said exact same string, it also meaning it's also case sensitive. Therefore, 'Hello world' or 'Hello everyone' will also not be counted.


The second anchor, '$' indicates that the last string must be the closing string.

This is similar to achor '^' but the opposite. 

For example, if we use '$' anchor as following:

```
    /dog$/
```
This would look for string that ends with its exact same string 'dog'. 
```
    catdog
```
but the string does not contain 'dog' in the last word will be not counted.
```
    dogcat
```

Since this is also case sensitive, 'catDog' will not be included. 


### Quantifiers
Quantifiers are used to define how many time should text(s)/character(s) should appear in regex match:

 * *   matches 0 or more occurrences,
 * +   matches 1 or more occurrence,
 * ?   matches 0 or 1 occurrences,
 * {}—Curly brackets set limits for a match:
    * {n}   matches exactly n occurrences,
    * {n,}   matches at least n occurences,
    * {m,n}   matches between m and n occurrences.

In this regular expression, 
    ```
        `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`
    ```
it uses '+' and the bound {2, 6} as its quantifiers. 
The first quantifier ([a-z0-9_\.-]+) and second quantifier ([\da-z\.-]+) use '+' quantifier, which means the string should match the pattern at least 1 or more.

So in our regex case with first quantifier,
```
    [a-z0-9_\.-]
```
the above pattern should match at least one or more of characters inside of the brackets []. (The details of Bracket Expression will be covered later of the content)

In our second quantifier,
```
    [\da-z\.-]
```
the above pattern should match at least one or more of characters inside of the brackets [].

For our third quantifier ([a-z\.]{2,6}), it uses curly brackets to set limits for pattern to be matched between 2 and 6 times. 

Therefore, third quantifier allows string to conatin any character of below range,
```
    [a-z\.]
```
but at least 2 characters to maximum 6 characters.

### Grouping Constructs

### Bracket Expressions

### Character Classes

### The OR Operator

### Flags
Regex has option to add flags which provides functionality 

### Character Escapes

## Author

Taeyoung Park

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
