# Test statements
## List
There is the list of test keywords in Nougaro :

| Nougaro   | Python    |
|-----------|-----------|
| if        | if        |
| then      | :         |
| elif      | elif      |
| else      | else      |

## Syntax

* `if <cond> then <expr>`
* `if <cond> then <expr> else <expr>`
* `if <cond> then <expr> elif <cond> then <expr>`
* `if <cond> then <expr> elif <cond> then <expr> else <expr>`
* `if <cond> then <expr> elif <cond> then <expr> elif <cond> then <expr>`
* `if <cond> then <expr> elif <cond> then <expr> elif <cond> then <expr> else <expr>`

etc.

Multi-line :
```nougaro
if <cond> then
    <some code here>
end
```

```nougaro
if <cond> then
    <some code here>
else
    <some other code>
end
```

```nougaro
if <cond> then
    <some code here>
else
    <some other code>
end
```

etc.

## Behaviour
The condition is checked. If it is true, the expression in the `if` branch is executed. Otherwise, Nougaro checks for an `elif` branch. If it exists, it re-checks the condition, etc. If none of the conditions is true and that there is an `else` branch, the expression in the `else` branch is executed. If there is no `else` branch, nothing is executed.

## Logicals constants

| Nougaro   | Python    | Comments                        |
|-----------|-----------|---------------------------------|
| True      | True      | equals to 1                     |
| False     | False     | equals to 0                     |

## Conditions
Conditions can be any [value](06values.md), which will be interpreted in its boolean context.

Conditions can also use [test operators](05operators.md#test-operators). For instance, `a == b` checks if `a` is equal to `b`, where `a < b` checks if `a` is strictly less than `b`. You can chain multiple operators: `a == b <= c != d` checks if `a` is equal to `b` and if `b` is less than or equal to `c` and if `c` is different from `d`.

Multiple conditions can be combined with [boolean/logical operators](05operators.md#logical-operators). Here is the truth table of the logical operators:

### `and`

| `a` | `b` | `a and b` |
|-----|-----|-----------|
|  0  |  0  |     0     |
|  0  |  1  |     0     |
|  1  |  0  |     0     |
|  1  |  1  |     1     |

### `or`

| `a` | `b` | `a or b`  |
|-----|-----|-----------|
|  0  |  0  |     0     |
|  0  |  1  |     1     |
|  1  |  0  |     1     |
|  1  |  1  |     1     |

### `xor`

| `a` | `b` | `a xor b` |
|-----|-----|-----------|
|  0  |  0  |     0     |
|  0  |  1  |     1     |
|  1  |  0  |     1     |
|  1  |  1  |     0     |

### `not`

| `a` | `not a` |
|-----|---------|
|  0  |    1    |
|  1  |    0    |

There is no priority amongst boolean operators, so for instance `a and b or c xor d` gives `((a and b) or c) xor d`.

After interpretation, a condition is always `0` or `1` (`False` or `True`).

## Examples

* `if foo == bar then var foo = 12`
* `if bar != foo then var foo = 12 else var bar = 13`
*
```nougaro
if foo > bar and 12 <= variable then
    var bar = variable
elif foo < bar xor foo > variable then
    var foo = 3
end
```

```nougaro
if foo > bar and 12 <= variable then
    var bar = variable
elif foo < bar xor foo > variable then
    var foo = 3
else
    var foo = 12
end
```
