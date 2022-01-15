# Title (replace with your title)

Introductory paragraph (replace this with your text)

## Summary

Regular Expression, or regex or regexp in short, is extremely and amazingly powerful in searching and manipulating text strings, particularly in processing text files. One line of regex can easily replace several dozen lines of programming codes.

Regex is supported in all the scripting languages (such as Perl, Python, PHP, and JavaScript); as well as general purpose programming languages such as Java; and even word processors such as Word for searching texts. 

## Example Regex Code Snippet
^(?=.*[A-Z].*[A-Z])(?=.*[!@#$&*])(?=.*[0-9].*[0-9])(?=.*[a-z].*[a-z].*[a-z]).{8}$

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

### Anchors

Anchors have special meaning in regular expressions. They do not match any character. Instead, they match a position before or after characters

- ^ – The caret anchor matches the beginning of the text.
    - let str = 'JavaScript';
      console.log(/^J/.test(str));

    - Output: true

- $ – The dollar anchor matches the end of the text.
    - let str = 'JavaScript';
      console.log(/^S/.test(str));

    - Output: false

### Quantifiers

Quantifiers match a number of instances of a character, group, or character class in a string.

A number in curly braces {n}is the simplest quantifier. When you append it to a character or character class, it specifies how many characters or character classes you want to match.

For example, the regular expression /\d{4}/ matches a four-digit number. It is the same as /\d\d\d\d/:

- let str = 'ECMAScript 2020';
  let re = /\d{4}/;

  let result = str.match(re);

  console.log(result); 

- Output: ["2020"]   


### Grouping Constructs

Groups regular expressions to capture sub strings of a string.

-   ()      - Matches the exact expression in the parentheses. For example, the pattern "(1-3)" matches "1-3" in "1-34", but nothing in "1".   

-   (?:)    - Creates a group that will not capture the string matched by the group.

-   (?<>)   - Creates a named capture group for future use in the regular expression.

-   \k<>    - References a named capture group created in the expression. Matches the string captured by that capture group.

### Bracket Expressions

Bracket expressions are a list of characters and/or character classes enclosed in brackets []. Use bracket expressions to match single characters in a list, or a range of characters in a list. If the first character of the list is the carat ^ then it matches characters that are not in the list.

- [abc]         - a, b, or c
- [a-z]	        - a through z
- [^abc]        - Any character except a, b, or c
- [[:alpha:]]   - Any alphabetic character (see below)

### Character Classes

A character class allows you to match any symbol from a certain character set. A character class is also called a character set.

-   .    - Matches any character except "\n". For example, the pattern "a.e" matches "ave" in "have" and "ate" in "water". To match a period character ".", precede the period with the escape character "\" to produce "\.".

-   []   - Matches any character in a set of characters. The characters are case-sensitive. For example, the pattern "[as]" matches "a" and "s" in "Laserfiche".

-   [^]  - Matches any character not in a set of characters. The characters are case-sensitive. For example, the pattern "[^as]" matches "L", "r", "f", "i", "c", and "h", and "e" twice in "Laserfiche".

-   "-"  - Matches any single character in the range from left to right. For example, the pattern "[A-X]" matches "X" in "XY".

-   \p{} - Matches any single character in the Unicode category. For example, the pattern "\p{IsCyrillic}" matches "Д" in "ДA".

-   \P{} - Matches any single character not in the Unicode category. For example, the pattern "\p{IsCyrillic}" matches "A" in "ДA".

-   \w   - Matches any word character. For example, the pattern "\w" matches "A", "B", "1", and "2" in "AB 1.2".

-   \W   - Matches any non-word character. For example, the pattern "\W" matches " " (blank space) and "." in "AB 1.2".

-   \s   - Matches any white-space character. For example, the pattern "\s" matches " " (blank space) in "AB 1.2".

-   \S   - Matches any non-white-space character. For example, the pattern "\s" matches "A", "B", "1", ".", and "2" in "AB 1.2".

-   \d   - Matches any decimal digit. For example, the pattern "\d" matches "1", "2", "3", and "4" in "ab 1.234".

-   \D   - Matches any non-decimal digit. For example, the pattern "\D" matches "a", "b", " " (blank space), and "." in "ab 1.234".   

### The OR Operator

Boolean Logic provides different operators where “or” operator is one of them. The regular expressions are used to match specific patterns by providing characters. The “or” operator can be used to provide options to match where one of the options should match provided with the “or” operator. The “or” operator is also called as “or” logic too. In this tutorial, we examine how to use “or” logic/operator with the regular expressions (regex).

The “|” is used as or logic operator. Multiple terms are provided by delimiting with the “|”. It is expected to match one of the provided terms. If one of the terms match the regular expression returns the matched part. The syntax of the “Or” logic is like below. Parenthesis is used to group terms to match as a whole.

- (TERM1|TERM2|TERM3|...)
    - TERM1, TERM2, TERM3 are character sets to match. Two or more terms can be used for a match.

### Flags

Flags, in a regular expression, are tokens that modify its behavior of searching. Flags are optional parameters that we can add to a plain expression to make it search in a different way. Each flag is denoted by a single alphabetic character, and serves different purposes in modifying the expression's searching behaviour.

For example the flag i, which stands for ignore casing, does the job of carrying out a case-insensitive search.

Similarly, the flag g, which stands for global, serves to extend the searching to find all matches for a given expression inside a string, instead of stopping on the first match.

- i - Ignore Casing: Makes the expression search case-insensitively.

- g	- Global: Makes the expression search for all occurences.

- s - Dot All: Makes the wild character . match newlines as well.

- m - Multiline: Makes the boundary characters ^ and $ match the beginning and ending of every single line instead of the beginning and ending of the whole string.

- y - Sticky: Makes the expression start its searching from the index indicated in its lastIndex property.

- u - Unicode: 	Makes the expression assume individual characters as code points, not code units, and thus match 32-bit characters as well. 

### Character Escapes

The backslash in a regular expression precedes a literal character. You also escape certain letters that represent common character classes, such as \w for a word character or \s for a space. The following example matches word characters (alphanumeric and underscores) and spaces.

Escaped Characters describes the escaped characters supported in JMP. \C, \G, \X, and \z are not supported.

- \\ - single backslash

- \A - start of a string

- \b - word boundary. The zero-length string between \w and \W or \W and \w.

- \B - not at a word boundary

- \cX - ASCII control character

- \d - single digit [0-9]

- \D - single character that is NOT a digit [^0-9]

- \E - stop processing escaped characters

- \l - match a single lowercase letter [a-z]

- \L - single character that is not lowercase [^a-z]

- \Q - ignore escaped characters until \E is found

- \r - carriage return

- \s - single whitespace character

- \S - single character that is NOT white space

- \u - single uppercase character [A-Z]

- \U - single character that is not uppercase [^A-Z]

- \w - word character [a-zA-Z0-9_]

- \W - single character that is NOT a word character [^a-zA-Z0-9_]

- \x00-\xFF - hexadecimal character

- \x{0000}-\x{FFFF} - Unicode code point

- \Z - end of a string before the line break

## Author

### Luis Gonzales  

Highly motivated IT Support professional with a working knowledge of common information technologies and systems management. Strong customer service and communication skills. Skilled in troubleshooting common IT problems in a fast-paced environment and rapidly adapting and mastering diverse new technologies and techniques.

<https://github.com/LuiGonz>
<https://www.linkedin.com/in/lugonzales/>
<https://luigonz.github.io/portfolio-project/?raw=true>

