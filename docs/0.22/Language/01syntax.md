# Very basic syntax

This document covers the basic syntax of Nougaro.

## Comments
There are two types of comments in Nougaro: single-line comments and multi-line comments.

### Single-line comments
Single-line comments start with `#` and end with a new line. They can start at the beginning of a line or after some code.

Example:
```nougaro
# this is a single-line comment
foo(bar)  # this calls the function foo with the argument bar
```

### Multi-line comments
Multi-line comments start with `/*` and end with `*/`. They can start and stop at any point in the code.

Example:
```nougaro
/* this is
a multi
line comment */

print("hello")  /* this is also a multi
line comment*/
```

Multi-line comments can also be only on one line:
```nougaro
print("hello")  /* this is a multi-line comment that is only on one line */
```

Multi-line comments are simply ignored, which mean you can do things such as:
```nougaro
print( /* this is a comment */ "hello" /* this is another comment */)
print(/*

this
is 
actually
a
comment*/ "hello")
```

Multi-line comments can be nested:
```nougaro
/* comment 
    /* comment-inside comment*/
    /*
       /* comment-ception */
    */
    comment
*/
```

## Lines
Line are separated by a newline or a semicolon (`;`).

```nougaro
a
b
```

is equivalent to `a ; b`.

## Line joining
If you don’t have enough space on your line, you can join two “real lines” to form a Nougaro line, using a backspace.

Example:
```nougaro
var fruits = [\
    "banana", \
    "apple", \
    "raspberry", \
    "pineapple" \
]
```

## Blank lines
Blank lines are ignored.

## Indentation
Indentation is optional, as (mostly) every statement ends with `end`.

## Whitespaces
Whitespaces are ignored everywhere (except in [string literals](03string_literals.md) and to differentiate things such as `foobar` and `foo bar`, or `+=` and `+ =`).
