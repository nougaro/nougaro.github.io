# Unicodedata

*[Source code](https://github.com/jd-develop/nougaro/blob/main/lib_/unicodedata_.py)*

!!! note "Credits"
    This is massively copied from [python documentation of unicodedata](https://docs.python.org/3/library/unicodedata.html), under the [Python Software Foundation License Version 2](https://www.python.org/download/releases/2.0/license/). © [Copyright](https://docs.python.org/3/copyright.html) 2001-2023, Python Software Foundation. This text has not been edited.

The `unicodedata` module can be imported with the statement `import unicodedata`.

The `unicodedata` provides access to the Unicode database.

## Constants
`unicodedata.unicodedata_version`: the version of the Unicode database used in this module. Depends on Python version!

## Functions
### `unicodedata.lookup`

Syntax: `unicodedata.lookup(name)`

Look up character by name. If a character with the given name is found, return the corresponding character. If not found, NotDefinedError is raised.

### `unicodedata.name`

Syntax: `unicodedata.name(chr, <default>)`

Returns the name assigned to the character `chr` as a string. If no name is defined, `default` is returned, or, if not given, RunTimeError is raised.

### `unicodedata.category`

Syntax: `unicodedata.category(chr)`

Returns the general category assigned to the character `chr` as string.

### `unicodedata.bidirectional`

Syntax: `unicodedata.bidirectional(chr)`

Returns the bidirectional class assigned to the character `chr` as string. If no such value is defined, an empty string is returned.

### `unicodedata.combining`

Syntax: `unicodedata.combining(chr)`

Returns the canonical combining class assigned to the character `chr` as integer. Returns 0 if no combining class is defined.

### `unicodedata.east_asian_width`

Syntax: `unicodedata.east_asian_width(chr)`

Returns the east asian width assigned to the character `chr` as string.

### `unicodedata.mirrored`

Syntax: `unicodedata.mirrored(chr)`

Returns the mirrored property assigned to the character `chr` as integer. Returns `1` if the character has been identified as a “mirrored” character in bidirectional text, `0` otherwise.

### `unicodedata.decomposition`

Syntax: `unicodedata.decomposition(chr)`

Returns the character decomposition mapping assigned to the character `chr` as string. An empty string is returned in case no such mapping is defined.

### `unicodedata.normalize`

Syntax: `unicodedata.normalize(form, unistr)`

Returns the normal form `form` for the Unicode string `unistr`. Valid values for `form` are ‘NFC’, ‘NFKC’, ‘NFD’, and ‘NFKD’.

The Unicode standard defines various normalization forms of a Unicode string, based on the definition of canonical equivalence and compatibility equivalence. In Unicode, several characters can be expressed in various way. For example, the character U+00C7 (LATIN CAPITAL LETTER C WITH CEDILLA) can also be expressed as the sequence U+0043 (LATIN CAPITAL LETTER C) U+0327 (COMBINING CEDILLA).

For each character, there are two normal forms: normal form C and normal form D. Normal form D (NFD) is also known as canonical decomposition, and translates each character into its decomposed form. Normal form C (NFC) first applies a canonical decomposition, then composes pre-combined characters again.

In addition to these two forms, there are two additional normal forms based on compatibility equivalence. In Unicode, certain characters are supported which normally would be unified with other characters. For example, U+2160 (ROMAN NUMERAL ONE) is really the same thing as U+0049 (LATIN CAPITAL LETTER I). However, it is supported in Unicode for compatibility with existing character sets (e.g. gb2312).

The normal form KD (NFKD) will apply the compatibility decomposition, i.e. replace all compatibility characters with their equivalents. The normal form KC (NFKC) first applies the compatibility decomposition, followed by the canonical composition.

Even if two unicode strings are normalized and look the same to a human reader, if one has combining characters and the other doesn’t, they may not compare equal.

### `unicodedata.is_normalized`

Syntax: `unicodedata.is_normalized(form, unistr)`

Return whether the Unicode string `unistr` is in the normal form `form`. Valid values for `form` are ‘NFC’, ‘NFKC’, ‘NFD’, and ‘NFKD’.
