# Regular Expressions (Regex) Guide

## Overview
* Regular Expressions (Regex); tools for pattern matching and text processing. 
* This guide was a cheatsheet for myself but I've decided to make it public, all the information can also be found on: [codepart.io](https://coderpad.io/blog/development/the-complete-guide-to-regular-expressions-regex/)

## 1. Basic Syntax
- `/pattern/` - Basic regex pattern.
- `/Hello|Goodbye/` - Matches either "Hello" or "Goodbye".
- `/\d{3}-\d{3}-\d{4}/` - Matches a phone number format.

### Example:
```regex
/Hello|Goodbye/
Matches: "Hello there", "Goodbye!"
Does not match: "Hi there"
```

## 2. Quantifiers
| Symbol  | Meaning |
|---------|---------|
| `?`     | Zero or one |
| `+`     | One or more |
| `*`     | Zero or more |
| `{N}`   | Exactly N times |
| `{N,}`  | N or more times |
| `{N,M}` | Between N and M times |

### Example:
```regex
Hello{1,3}
Matches: "Hello", "Helloo", "Hellooo"
Does not match: "Helloooo"
```

## 3. Character Classes
| Symbol | Meaning |
|--------|---------|
| `[A-Z]` | Any uppercase letter |
| `[a-z]` | Any lowercase letter |
| `[0-9]` | Any digit |
| `[aeiou]` | Any vowel |
| `[^a-z]` | Not a lowercase letter |

### Example:
```regex
[A-Z][a-z]+
Matches: "Hello", "Goodbye"
Does not match: "hello", "123"
```

## 4. Special Characters
| Symbol  | Meaning |
|---------|---------|
| `.`     | Any character |
| `\n`    | Newline |
| `\t`    | Tab |
| `\s`    | Whitespace |
| `\S`    | Non-whitespace |
| `\w`    | Word character (letters, digits, `_`) |
| `\W`    | Non-word character |
| `\b`    | Word boundary |
| `^`     | Start of line |
| `$`     | End of line |

### Example:
```regex
\bHello\b
Matches: "Hello there"
Does not match: "Helloo there"
```

## 5. Groups & Capture Groups
- `(abc)` - Captures `abc`
- `(?:abc)` - Non-capturing group
- `(?<name>abc)` - Named capture group

### Example:
```regex
(Hello|Hi) there
Matches: "Hello there", "Hi there"
```

## 6. Lookaheads & Lookbehinds
| Symbol  | Meaning |
|---------|---------|
| `(?=abc)`  | Positive lookahead |
| `(?!abc)`  | Negative lookahead |
| `(?<=abc)` | Positive lookbehind |
| `(?<!abc)` | Negative lookbehind |

### Example:
```regex
Hello(?= World)
Matches: "Hello World"
Does not match: "Hello there"
```

## 7. Flags
- `/pattern/g` - Global match (find all matches)
- `/pattern/i` - Case-insensitive match
- `/pattern/m` - Multiline mode

### Example:
```regex
/hello/i
Matches: "hello", "Hello", "HELLO"
```

## 8. String Replacement with Regex (JavaScript Example)
```js
let str = "Hello, Hi there!";
str = str.replace(/[Hh]ello|[Hh]i|[Hh]ey/g, "Goodbye");
console.log(str); // "Goodbye, Goodbye there!"
```

## 9. Named Capture Groups
```regex
/(?<num>\d{3})/
Matches: "123", "456"
Reference: $<num>
```

## 10. Example: Matching a Phone Number
```regex
^(?:\d{3}-){2}\d{4}$
Matches: "555-555-5555"
Does not match: "555-abc-5555"
```
