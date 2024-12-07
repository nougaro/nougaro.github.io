# Loops

Loops are made to execute the same piece of code multiple times in a row. Here is a list of available loops in Nougaro:

| Nougaro                         | Python       | C/C++               |
|---------------------------------|--------------|---------------------|
| [`for`](#for)                   | `for`        | `for`               |
| [`while`](#while)               | `while`      | `while`             |
| [`do ... then loop while`](#do) | (nothing)    | `do ... while`      |
| [`loop`](#loop)                 | `while True` | `while (1)`

## `for`
The for loop can have two usages: browse every element in a [list](06values.md#lists) (or a [str](06values.md#strings)), or iterate a certain number of times.

### for each
To browse every element in a [list](06values.md#lists) (or a [str](06values.md#strings)), use the following syntax:

```nougaro
# One line
for identifier in list then ...

# Multiple lines
for identifier in list then
   ...
   ...
end
```

For each element of the list, the [variable](07variables.md) `identifier` will be set to the corresponding element, and this variable can be used inside the loop.

### `for i = ... to ...`

```nougaro
# One line
for identifier = start_value to end_value then ...
for identifier = start_value to end_value step step_value then ...

# Multiple lines
for identifier = start_value to end_value then
    ...
    ...
end

for identifier = start_value to end_value step step_value then
    ...
    ...
end
```

`start_value`, `end_value` and `step_value` are [integers](06values.md#numbers). If `step_value` is not specified, the default value is 0.

This loop starts by setting the variable `identifier` to `start_value`, then executes the loop. It then adds `step_value` to `identifier`. If the value of `identifier` is greater than or equal to `end_value`, the loops stops without executing. Otherwise, it runs until this condition is reached.

!!! note
    In `for` loops, the start value can be less than the end value. In that case, don’t forget to give a negative step!

## `while`

The `while` loop is used to repeat a piece of code as long as a [condition](08tests.md#conditions) is met. It has the following syntax:
```nougaro
# One line
while condition then ...

# Multiple lines
while condition then
    ...
    ...
end
```

## `do`
The `do` loop is used to execute a piece of code a first time, then repeat it as long as a [condition](08tests.md#conditions) is met. It has the following syntax:
```nougaro
# One line
do ... then loop while condition

# Multiple lines
do
    ...
    ...
then loop while condition
```

## `loop`
!!! note "Added in 1.1.0"
    The `loop` loop was added in 1.1.0

The `loop` loop is an infinite loop. It has the following syntax:
```nougaro
# One line
loop ...

# Multible lines
loop
    ...
    ...
end
```

The `loop` loop stops whenever it encounters a `break` (like every other loop)

## Labels
!!! note "Added in 0.20.0-beta"
    Labels were added in 0.20.0-beta.

You can label a loop using `for:label`, `while:label` or `do:label`. Labels are [identifiers](04identifiers_and_keywords.md). You can use labels with `break` and `continue`.

## `break`, `continue`
!!! note "Changed in 0.20.0-beta"
    Prior to 0.20.0-beta, `break` and `continue` did append [`None`](06values.md#none) to the return list. To re-enable this behaviour, you can enable `appendNoneOnBreak` or `appendNoneOnContinue` [metas](15metas.md).
!!! note "Added in 0.20.0-beta"
    Labels were added in 0.20.0-beta.

* The `break` statement completely stops the loop. If there is a returned list, the value is not added to this list. You can use `break and return ...` to return a specific value.
* The `continue` statement omit the code after it, and execute another time the loop like if the last time was ended.
* `continue` and `break` work normally at the first execution of a `do` body.
* `continue:label` will continue the loop that has this label. If you’re in an `:inner` loop inside a `:label` loop, the `:inner` loop will break and the `:label` loop will continue.
* `break:label` will break the loop that has this label. If you’re in an `:inner` loop inside a `:label` loop, the `:inner` AND the `:label` loop will break.
