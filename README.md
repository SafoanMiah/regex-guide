# Regular Expressions (Regex) Guide

## Overview
* Regular Expressions (Regex); tools for pattern matching and text processing. 
* This guide was a cheatsheet for myself but I've decided to make it public.
* All the information can also be found on: [codepart.io](https://coderpad.io/blog/development/the-complete-guide-to-regular-expressions-regex/)

## 1. Basic Syntax
- `/pattern/` - Basic regex pattern.
- `/Hello|Goodbye/` - Matches either "Hello" or "Goodbye".
- `/\d{3}-\d{3}-\d{4}/` - Matches a phone number format.

## 2. Quantifiers
| Symbol  | Meaning |
|---------|---------|
| `?`     | Zero or one |
| `+`     | One or more |
| `*`     | Zero or more |
| `{N}`   | Exactly N times |
| `{N,}`  | N or more times |
| `{N,M}` | Between N and M times |

## 3. Character Classes
| Symbol | Meaning |
|--------|---------|
| `[A-Z]` | Any uppercase letter |
| `[a-z]` | Any lowercase letter |
| `[0-9]` | Any digit |
| `[aeiou]` | Any vowel |
| `[^a-z]` | Not a lowercase letter |

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

## 5. Groups & Capture Groups
- `(abc)` - Captures `abc`
- `(?:abc)` - Non-capturing group
- `(?<name>abc)` - Named capture group

## 6. Lookaheads & Lookbehinds
| Symbol  | Meaning |
|---------|---------|
| `(?=abc)`  | Positive lookahead |
| `(?!abc)`  | Negative lookahead |
| `(?<=abc)` | Positive lookbehind |
| `(?<!abc)` | Negative lookbehind |

## 7. Flags
- `/pattern/g` - Global match (find all matches)
- `/pattern/i` - Case-insensitive match
- `/pattern/m` - Multiline mode

## 8. Named Capture Groups
- `(?<name>...)` - Named capture group
- `\k<name>` - Reference named capture group in a query

## 9. Example: Matching a Phone Number
- `^(?:\d{3}-){2}\d{4}$` - Matches phone numbers like `555-555-5555`
