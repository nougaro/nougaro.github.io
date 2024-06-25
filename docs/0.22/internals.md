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

## Nougaro informations
!!! note
    This section is duplicated in [this file](stdlib/01builtin-variables.md)

* `__noug_version__`: string of the Nougaro version (e.g. "0.15.0-beta".) You can use the [`noug_version`](https://github.com/jd-develop/nougaro/wiki/noug_version) lib to have better informations.
* `__data_version__`: the Nougaro data version, an internal version keeping track of changes in the config file directory structure
* `__version_id__`: an ID increased at least once per version
* `__python_version__`: string of the Python version (e.g. "3.10.5")
* `__noug_dir__`: string of the absolute path of the directory where shell.(py/exe/bin) is located. May be used with file I/O `read` and `write` statements.

## Symbol table
* `__symbol_table__` : string of the internal “p-formated” symbols dictionnary.
