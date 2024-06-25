# Internals

Features that had to be documented but that are mainly used for debugging purposes.

## Context variables
* `__actual_context__` is the name of the function where the code is executed. May be `<program>`.
* `__exec_from__` is the name of the parent of the function where the code is executed.
    * If `__actual_context__` is `<program>`, `__exec_from__` is `(shell)`.
    * If the code is inside a [function](Language/10functions.md) `foo` that is directly in `<program>`, `__exec_from__` is `foo from <program>`.
    * If the code is inside a [function](Language/10functions.md) `bar` executed from our `foo` (that is in `<program>`), `__exec_from__` is `bar from foo`.

## Base value
* `__base_value__` is the base value (python class `Value`). It is the parent class of all the other values. It is the only value to crash on `==` and `!=` [operators](Language/05operators.md#logical-operators).
