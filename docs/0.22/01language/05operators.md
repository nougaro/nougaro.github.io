# Operators

## Mathematical operators
Here all the mathematical operators in Nougaro (ordered by priority):

| Nougaro   | Python    | Comments                        |
|-----------|-----------|---------------------------------|
| `^`       | `**`      | power                           |
| `*`       | `*`       | multiplication                  |
| `%`       | `%`       | modulo                          |
| `/`       | `/`       | division                        |
| `//`      | `//`      | floor division                  |
| `+`       | `+`       | addition                        |
| `-`       | `-`       | substraction                    |
| `&`       | `&`       | bitwise and                     |
| `|`       | `|`       | bitwise or                      |
| `^^`      | `^`       | bitwise xor                     |
| `~`       | `~`       | bitwise not                     |

It respects operation priority and you can use parenthesis.

### Examples

* `3 * 4` returns 12
* `4 / 2` returns 2
* `1 + 1` returns 2
* `3 - 4` returns -1
* `10 % 7` returns 3
* `10 % 3` returns 1
* `10 // 7` returns 1
* `10 // 3` returns 3
* `5 ^ 2` returns 25
* `62 & 35` returns 34
* `~1` returns -2 and `~-2` returns 1

* `5 + 5 * 3 + 2` returns 22
* `(5 + 5) * (3 + 2)` returns 50

## Test operators
They are exactly same as Python ones:

| Nougaro   | Python    | Comments                        |
|-----------|-----------|---------------------------------|
| `==`      | `==`      | equals to                       |
| `!=`      | `!=`      | different than                  |
| `<`       | `<`       | less than                       |
| `<=`      | `<=`      | less than or equals             |
| `>`       | `>`       | greater than                    |
| `>=`      | `>=`      | greater than or equals          |
| `in`      | `in`      | check if a value is in another  |

!!! note
    the `in` keyword can check if:

    * `int`, `float`, `str`, `list`, `DefaultValue` or `NoneValue` is in a `str`
    * any value is in a `list`

    !!! info "Added in 0.22.0-beta"
        `DefaultValue` is new in 0.22.0-beta.

## Logical operators
There is one logical operator that isn't here in Python. There is a list:

| Nougaro   | Python    | Comments                        |
|-----------|-----------|---------------------------------|
| `and`     | `and`     | boolean 'and'                   |
| `or`      | `or`      | boolean 'or'                    |
| `xor`     | `^`       | boolean 'exclusive or'          |
| `not`     | `not`     | boolean 'not' (inverter)        |
