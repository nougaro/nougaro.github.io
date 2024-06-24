# Variables

## Definition
Use the syntax `var identifier = value` (see [identifiers](04identifiers_and_keywords.md) and [values](06values.md)) to assign the value `value` to the variable named `identifier`. The expression `var identifier = value` returns `value`.

To assign the same value to multiple variables, you can use `var variable1 = var variable2 = var variable3 = value`.

If you want to assign multiple values to multiple variables, you can use `var variable1, variable2 = value1, value2`. This can be used to swap variables: `var a, b = b, a`.

Except for [keywords](04identifiers_and_keywords.md#keywords), there are no prohibited variable name.

## Edition
You can edit variables by multiple ways:

* `var a = value`;
* `var a += value`: same as `var a = a + value`;
* `var a ++`: same as `var a += 1`;
* `var a -= value`: same as `var a = a - value`;
* `var a --`: same as `var a -= 1`;
* `var a *= value`: same as `var a = a * value`;
* `var a /= value`: same as `var a = a / value`;
* `var a ^= value`: same as `var a = a ^ value`;
* `var a //= value`: same as `var a = a // value`;
* `var a %= value`: same as `var a = a % value`;
* `var a ||= value`: same as `var a = a or value`;
* `var a &&= value`: same as `var a = a and value`;
* `var a ^^^= value`: same as `var a = a xor value`;
* `var a |= value`: same as `var a = a | value`;
* `var a &= value`: same as `var a = a & value`;
* `var a ^^= value`: same as `var a = a ^^ value`;
* `var a === value`: same as `var a = a == value`;
* `var a <== value`: same as `var a = a <= value`;
* `var a <<= value`: same as `var a = a < value`;
* `var a >== value`: same as `var a = a >= value`;
* `var a >>= value`: same as `var a = a > value`.

!!! info
    For details about these operators, see [this page](05operators.md).

!!! note
    You can also edit multiple variables at the same time:

    * `var a, b += 1, 2`: same as `var a += 1 ; var b += 2`
    * `var a, b ++`: same as `var a, b += 1, 1`
    * `var a, b //= b, a`: same as `var c = a ; var a //= b ; var b //= c ; del c`

## Access
To access to a variable, you can:

* give the identifier: `foo` (returns the value of `foo`)
* use the special syntax: `foo ? bar ? a ? b` (returns the value of `foo` if it is defined, otherwise the value of `bar`... You can put as much `? identifier` as you want.) Then, you can put an expression at the end, such as `2`. In this case, the value returned will be `2` if none of the given identifiers is defined.

## Deletion
If you don't need a variable anymore, you can delete it with the `del` keyword: `del identifier`.

## Examples
* `var foo = var bar = 12`
* `while foo != bar - 1 then var bar -= 1` (see [while loop](link-to-loops.md#while))

### Example for deletion

Create a variable `a`, the delete it:
```nougshell
nougaro> var a = 1
1
nougaro> del a
```

But be careful! It can return errors:
```nougshell
nougaro> var a = 1
1
nougaro> del a
nougaro> del a
Traceback (more recent call last):
 In file <stdin>, line 1, in <program>:

  del a
      ^
 NotDefinedError: a is not defined.
```
