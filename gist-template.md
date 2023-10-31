# Title: Explaining  Regular Expressions

It all comes down to pattern matching with text. This gist is about understanding each component, what it is and does, etc.

## Summary
For this assignment, I chose to use this regular expression: `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})/`. This is the one that is responsible for matching email addresses. Refer to the table of contents below for a further explanation of each of the components that make up a regular expression. We will go over each in detail.

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

In the given expression that I discussed in the introduction, they use Anchors (`^` and `$`). These signify where a string begins and ends. This one `^` appears at the beginning of a string, and `$` appears at the end of a string.

**Example:**
- `^Adam.Olson@gmail.com$`

### Quantifiers

Quantifiers tell you how many times a character shows up in a string. These are the most common examples.

- `*` - Matches zero or more occurrences.
- `+` - Matches one or more occurrences.
- `?` - Matches zero or one occurrence (optional).
- `{n}` - Matches exactly n occurrences.
- `{n,}` - Matches n or more occurrences.
- `{n,m}` - Matches between n and m occurrences.

**Example:**
- `mystical-dragon@gmail.com`: `([a-z0-9_\.-]+)` matches 'mystical-dragon'. This ensures that there is one or more lowercase letters, digits, underscores, hyphens, or dots.

### OR Operator

The OR Operator (`|`) allows you to match one of several alternatives. It's like having multiple options for a specific part of your pattern. For example, you can match 'wizard' or 'sorcerer' in a text.

**Example:**
- `(wizard|sorcerer)@fantasy-realm.com` matches either 'wizard@fantasy-realm.com' or 'sorcerer@fantasy-realm.com' in an email address.

### Character Classes

Character Classes allow you to match specific characters or ranges of characters. For instance, you can match any vowel in a string.

**Example:**
- `[aeiou]@magical-vowels.com` matches any single vowel followed by '@magical-vowels.com' in an email address.

### Flags

Flags change the behavior of a regex pattern. The `i` flag makes the pattern case-insensitive, allowing you to match text regardless of letter case.

**Example:**
- `/wizard/i@fantasy-magic.org` matches 'Wizard@fantasy-magic.org' case-insensitively.

### Grouping and Capturing

Grouping and capturing are used to extract specific parts of a pattern. They are enclosed in parentheses `()`. For instance, you can capture a hero's name from a superhero-themed email address.

**Example:**
- `(superman|batman)@(heroes).com` captures the hero's name and 'heroes' in 'superman@heroes.com'.

### Bracket Expressions

Bracket expressions allow you to match a range of characters. You can match any single digit in a string.

**Example:**
- `[0-9]@digit-domain.com` matches any single digit followed by '@digit-domain.com' in an email address.

### Greedy and Lazy Match

Greedy matching is the default behavior of regex, where it matches as much as possible. Lazy matching, denoted by `?`, matches as little as possible. This can be used to match text within HTML tags.

**Example:**
- `<.*?>` matches the text within the first HTML tag in a document. Lazy match ensures it doesn't match the entire document.

### Boundaries

Boundaries, such as `\b`, match specific positions in the string. They can be used to match whole words. For example, you can match 'magic' as a whole word in a text.

**Example:**
- `\bmagic\b@spellbook.com` matches 'magic' as a whole word, not as part of another word, followed by '@spellbook.com'.

### Back-references

Back-references allow you to match a previously captured group again within the same regex. This is particularly useful for matching repeating patterns.

**Example:**
- `(\d{2})-(\1)@repeating-numbers.com` matches '12-12@repeating-numbers.com', where the same two digits are repeated.

### Look-ahead and Look-behind

Look-ahead and look-behind are used to assert that a pattern is or isn't followed by specific text, without including that text in the match. For example, you can match an email address only if it's followed by '@example.com'.

**Example:**
- `johndoe(?=@example.com)` matches 'johndoe' only if it's followed by '@example.com'.

## Author


