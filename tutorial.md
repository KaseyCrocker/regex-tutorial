# Regex Tutorial

Regex is short for 'Regular Expressions' is way to search through a string of text in order to do things such as vlaidation, get certain pieces of text, advances find and replace, ect... It allows you to extract information form any text by searching for matches of a specific search pattern.
Regex is commonly used to validate input such as emails:
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

## Table of Contents

- [Anchors and Boundaries](#anchors-and-boundaries)
- [Quantifiers and Alternation](#quantifiers-and-alternation)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

### Anchors and Boundaries
Anchors indicates the beginning, end, and boundaries of the expressions
- `^` indicates the beginning of the string.
    `^\w+` `she` sells seashells
- `$` indicates the end of the string.
    `\w+$` she sells `seashells`
- `\b` indicates word boudaries
    `s\b` she sell`s` seashell`s`
- `s\B` indicates not word boundaries
    `s\B` `s`he `s`ells `s`ea`s`hells

### Quantifiers and Alternation
Quantifiers indicate how many characters to search for. By default, they will try to match as many characters as possible.
- plus `+` matches 1 or more of the preceding token.

    `b\w+` b `be` `bee` `beer` `beers`
- star `*` Matches 0 or more of the preceding token.

    `b\w*` `b` `be` `bee` `beer` `beers`
- quantifier `{1,3}` Matches the specified quantity of the previous token. {1,3} will match 1 to 3. {3} will match exactly 3. {3,} will match 3 or more.

    `b\w{2,3}` b be `bee` `beer` `beer`s
- optional `?` Matches 0 or 1 of the preceding token, effectively making it optional.

    `colou?r` `color` `colour`
- lazy `?` Makes the preceding quantifier lazy, causing it to match as few characters as possible. By default, quantifiers are greedy, and will match as many characters as possible.

    `b\w+?` b `be` `be`e `be`er `be`ers
- alternation `|` Acts like a boolean OR. Matches the expression before or after the |.
It can operate within a group, or on a whole expression. The patterns will be tested in order.

    `b(a|e|i)d` `bad` bud bod `bed` `bid`

### Character Classes
- `[ABC]` and `[^ABC]` include or exclude the letters inside the brackets.

    `[aeiou]` gl`i`b j`o`cks v`e`x dw`a`rv`e`s!
- `[A-Z]` indicates a range of letters within the barckets.

    `[g-s]` abcdef`ghijklmnopqrs`tuvwxyz
- `\w` and `\W` indicates either non alphabetical word characters `(!,^#$@)`, or alphabetical word characters `(a-z)`.
- `\d` and `\D` indicates either numerical digits [0-9] or non-numerical characters [^0-9].
- `\s` and `\S` indicates either whitespace (spaces) or not whitespace.

### Flags
- ignore case `i` Makes the whole expression case-insensitive. For example, `/aBc/`i would match `AbC`.
- global search `g` Retain the index of the last match, allowing subsequent searches to start from the end of the previous match.
- multiline `m` When the multiline flag is enabled, beginning and end anchors (`^` and `$`) will match the start and end of a line, instead of the start and end of the whole string.
- unicode `u` When the unicode flag is enabled, you can use extended unicode escapes in the form `\x{FFFFF}`.
- sticky `y` The expression will only match from its lastIndex position and ignores the global (`g`) flag if set.
- dotall `s` Dot (`.`) will match any character, including newline.

### Grouping and Capturing
- capturing `(ABC)` Groups multiple tokens together and creates a capture group for extracting a substring or using a backreference.

    `(ha)+` `hahaha` `ha`a `ha`h!
- named cpturing `(?<name>ABC)` Creates a capturing group that can be referenced via the specified name.
- non-capturing `(?:ABC)` Groups multiple tokens together without creating a capture group

    `(?:ha)+` `hahaha` `ha`a `ha`h!

### Back-references
- numeric refernce `\1` Matches the results of a capture group. For example `\1` matches the results of the first capture group & `\3` matches the third.

    `(\w)a\1` `hah` `dad` bad dab `gag` gab

## Author

[Kasey Crocker](https://github.com/KaseyCrocker)

I'm an aspiring developer looking to enter the world of web development. I've always been a very analytical person and problem solving has always peaked my interest. I seem to gravitate towards the server side of development due to its structure and consistency. I am currently hunting for an established company with the infrastucture to allow me, a junior developer, to esablish a foundation and learn from more experienced developers.