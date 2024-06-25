# Functions

Internal type: `func`.

No [operation](05operators.md) can be used on functions.

Functions are true in boolean context.

!!! note "Changed in 0.22.0-beta"
    Prior to 0.22.0-beta, functions were false in boolean context.

## Definition

To define a function, use the `def` [keyword](04identifiers_and_keywords.md#keywords) and an arrow: `def name(param1, param2) -> <some code here>`.
You can omit the name, but in this case you have to call directly the function or to store it in a variable: `(def (param1) -> <some code here>)(<arg1>)`; `var somefunc = def (param1) -> <some code here>`

You can define multi-line functions:
```nougaro
def name(param1, param2, param3)
    <some code here>
end
```

!!! note
    The arguments given and the variables created inside the function are deleted at the end of the function execution. Similarly, the variables created outside the function and before its definition are accessible inside the function, but modifications are not saved.

!!! info
    There can be 0 parameters.

## Optional parameters
!!! note
    Added in 0.22.0-beta

To define optional parameters, use this syntax:
```nougaro
def name(param1, param2, param3)(optional_param1=default_value, optional_param2=default_value)
    <some code here>
end
```

## `return` statement

In the code executed by your function, there can be the `return` statement. It stops the function. If a value is placed after the statement, the function will return this value when called. In the other cases, it will return [`None`](06values.md#none).

## Call

* Call a function using this syntax: `func(arg1, arg2)`
* You can store arguments in a list and use `*list`. E.g. `func(*list_)`, `func(*[1, 2, 3])`.

### Optional arguments
!!! note
    Added in 0.22.0-beta

* You can omit optional arguments, which will set them to their default value.
* In this case: `def name(param1, param2, param3)(optional_param1=default_value, optional_param2=default_value)`, if you want to keep `optional_param1` to its default value but not `optional_param2`, you can use: `name(argument1, argument2, argument3, <default>, optional_argument2)` (keep `<` and `>` around `<default>`)

## Examples

```nougaro
def foo(a, b) -> a*b - b
def bar(a, b) -> (a-1)*b
var c = 2
var d = 5
if foo(c, d) == bar(c, d) then var e = True else var e = False
```
(In this case, e = 1)

```nougaro
def foo(a, b)
    if a == 2 then
        return a + b
    else
        return b
    end
end
```

```nougaro
def foo(a, b)(should_return_none = False)
    if a == 2 then
        return a + b
    else
        if should_return_none then return
        return b
    end
end

foo(1, 5)  # 5
foo(2, 5)  # 7
foo(1, 5, <default>)  # 5
foo(2, 5, <default>)  # 7
foo(1, 5, True)  # None
foo(2, 5, True)  # 7
```
