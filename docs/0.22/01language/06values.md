# Values

Here is the list of the value types in Nougaro:

* int ([integers](#numbers)). Internal type: `int`
* float ([floats](#numbers)). Internal type: `float`
* str ([strings](#strings)). Internal type: `str`
* list ([lists](#lists)). Internal type: `list`
* NoneType ([None](#none)). Internal type: `NoneValue`
* [function](link-to-functions). Internal type: `func`.
* [module](link-to-modules). Internal type: `module`
* [constructor](link-to-objects). Internal type: `constructor`
* [object](link-to-objects). Internal type: depends on the class’ name, and it is `<class>` if the class has no name.

!!! note
    Internal value types are base value (type: `BaseValue`) and default value (type: `DefaultValue`)

!!! warning
    Before 0.22.0-beta, a distinction was made between `func` (user-defined function or function in a module written in Nougaro) and `built-in func` (built-in function or function in a module written in Python)

## Numbers
Numbers represents real-life numbers. The two types of numbers are `int` and `float`.

To declare a number, you can use a [number literal](02number_literals.md).

[Operations](05operators.md) that can be used between two numbers are: addition, substraction, multiplication, power.
If the second number is non-zero, division, modulo and floor division can be used.
All these operations follow the mathematical logic (except for 0^0, that returns 1).

Multiplication can be used between a integer (type `int`) and a [string](#strings) or a [list](#lists). For example, `3*"str"` returns `"strstrstr"`, and `2*[1, 2]` returns `[1, 2, 1, 2]`.

In boolean context, a number is true if it is non-zero.

## Strings
The type of a string is `str`.

To declare a string, you can use a [string literal](03string_literals.md)

The only [operation](05operators.md) that can be used between strings is addition, which concatenates the string with the other. For example, `"hello, " + "world!"` returns `"hello, world!"`.

Multiplication can be used between a string and an [integer](#numbers) (type `int`). For example, `"str"*3` returns `"strstrstr"`.

In boolean context, a string is true if it contains at least one character.

## Lists
Lists are a succession of values.

To declare a list, you can use brackets (`[]`), and put every value separated by a comma (`,`) inside.

The only [operation](05operators.md) that can be used between two lists is multiplication, which extends the first list with the content of the second list.

Addition can be used between a list and any other value to add an element to the list.

Substraction can be used between a list and an [integer](#numbers) (type `int`) to pop (i.e. delete) an element by index. This supports negative numbers.

Multiplication can be used between a list and an [integer](#numbers) (type `int`). For example, `[1, 2]*2` returns `[1, 2, 1, 2]`.

Division can be used between a list and an [integer](#numbers) (type `int`) to get an element by index. This supports negative numbers.

In boolean context, a list is true if it is not empty

## None
None is a value to denote the absence of other values.

It is accessible trought the `None` built-in variable.

No [operation](05operators.md) can be used on `None`.

In boolean context, `None` is false.
