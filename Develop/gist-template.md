# Regex Tutorial (What is Regex?)

Regex or Regular Expressions is a sequence of characters that specifies a match pattern in string. Regex is helpful when user wants to apply filter to search and manipulate text used for programming languages and applications, such as finding/validating matching string or characters in email, hex value, URL tag, HTML tag, and etc. 

This Regex Tutorial is to explain how Regex works by breaking down each part of the expression.

## Summary

The contents of the tutorial is to help anyone who wants to undesrtand to how to use regex or who wants to use/create their own regex combination. 

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

When we say exact same string, it means it's also case sensitive. Therefore, 'hello' with uppercase such as 'Hello world' or 'Hello everyone' not match the pattern.


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
If we want to use regex with different patterns for multiple parts, Grouping Constructs (parentheses) can be used to separate these sections. 

The regex example we are using here shows three different sections:
```
    /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```

```
    ([a-z0-9_\.-]+)
    ([\da-z\.-]+)
    ([a-z\.]{2,6})
```
Also notice our expression shows that it must include '@' between first group and second group, and must include '.' between second group and third group.

### Bracket Expressions
For Bracket Expression ([]), think of the array list. Bracket expression allows us to write all of the characters we wants to include and match. 

In our regex, 

The first section has following bracket expression,
```
    [a-z0-9_\.-]
```
This indicates that in this expression, it includes all characters from a-z, all number from 0-9, underscore(_), period(\.), and dash(-).

The second section has following bracket expression,
```
    [\da-z\.-]
```
In this expression, it includes all numberic number(\d will be discussed later), all characters a-z, period(\.), and dash(-).

And finally, our third section has following bracket expression,
```
    [a-z\.]
```
This includes all characterse from a-z and period(\.).

So far, by looking at our regex, we can tell that, 
    - first group is expression for name of the email that includes at least one or more of chracters inside of that bracket.
    - after adding '@'
    - second group is expression for email address domain name (ex: 'gmail' if email address domain is 'gmail.com')
    - after adding '.'
    - third group is expression for email address domain extension (ex: '.com' or '.edu')


### Character Classes

Character Classes are predefined sets of characters. Belows are some of the character classes:

* . —Matches everything except the newline character (\n)

* \d —Matches to any numeric number (= [0-9]).

* \w —Matches any alphanumeric character from the basic Latin alphabet, including the underscore (_). (= [A-Za-z0-9_]).

* \s —Matches a single whitespace character, including tabs and line breaks

As mentioned previously, in our example regex expression, 
```
    /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```
in the second group bracket expression, it has '\d' which matches to number number [0-9]

### The OR Operator

Regex has 

### Flags
Regex has option to add flags which provides extra functionality or limit to the expression. Unlike other regex components, flag must be added after end of the literal slash. 

Belows are few options of flags:

* g —Global search: the regex should be tested against all possible matches in a string.

* i —Case-insensitive search: case should be ignored while attempting a match in a string

* m —Multi-line search: a multi-line input string should be treated as multiple lines

In our regex expression, it doesn't not contain any flags.

### Character Escapes



## Author

Tutorial written by Taeyoung Park, a web development student. (Github: [@TaeyoungP](https://github.com/taeyoungP), Email: taeyoung.park@uconn.edu)

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
