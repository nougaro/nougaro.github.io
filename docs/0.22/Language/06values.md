# Values

Here is the list of the value types in Nougaro:

* int ([integers](#numbers)). Internal type: `int`
* float ([floats](#numbers)). Internal type: `float`
* str ([strings](#strings)). Internal type: `str`
* list ([lists](#lists)). Internal type: `list`
* NoneType ([None](#none)). Internal type: `NoneValue`
* [function](10functions.md). Internal type: `func`.
* [module](#modules). Internal type: `module`
* [constructor](11classes.md#constructor-value). Internal type: `constructor`
* [object](11classes.md#object). Internal type: depends on the class’ name, and it is `<class>` if the class has no name.

!!! note
    Internal value types are base value (type: `BaseValue`) and default value (type: `DefaultValue`)

    !!! info "Added in 0.22.0-beta"
        `DefaultValue` is new in 0.22.0-beta.

!!! info "Changed in 0.22.0-beta"
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

To declare a list, you can use brackets (`[]`), and put every value separated by a comma (`,`) inside. They may be 0 values.
To create a list with elements from another list (and other elements), you can use this syntax: `[1, 2, *list_, 5]` (which is `[1, 2, 3, 4, 5]` if `list_` is `[3, 4]`).

The only [operation](05operators.md) that can be used between two lists is multiplication, which extends the first list with the content of the second list. This can also be achieved using [`extend(list1, list2)`](../stdlib/02builtin-functions.md#extend)

Addition can be used between a list and any other value to add an element to the list.

Substraction can be used between a list and an [integer](#numbers) (type `int`) to pop (i.e. delete) an element by index. This supports negative numbers. The returned value is the list after the pop. This can be achieved with [`pop(list, index)`](../stdlib/02builtin-functions.md#pop), although this returns the popped value.

Multiplication can be used between a list and an [integer](#numbers) (type `int`). For example, `[1, 2]*2` returns `[1, 2, 1, 2]`.

Division can be used between a list and an [integer](#numbers) (type `int`) to get an element by index. This supports negative numbers. This can be achieved using `list[index]` or [`get(list, index)`](../stdlib/02builtin-functions.md#get).

In boolean context, a list is true if it is not empty

## None
None is a value to denote the absence of other values.

It is accessible trought the `None` built-in variable.

No [operation](05operators.md) can be used on `None`.

In boolean context, `None` is false.

## Modules
A module is a value containing various useful functions and constants. A list of modules can be found [here](../stdlib/modules/index.md). Importing modules is detailed [here](13import.md). The procedure to create your own module is detailed [here](../Expanding/Write-libs.md).

No [operation](05operators.md) can be used on modules.

In boolean context, a module is true.

!!! note "Changed in 0.22.0-beta"
    Prior to 0.22.0-beta, a module was false in boolean context.
