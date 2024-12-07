# List of built-in functions

!!! note
    In this page, type of parameters are noted using the `param: type` syntax (type can eventually be `Any`), and optional parameters are noted between `<>` and their default value are specified with `=`.
    Also, `*args` tells that this function can take any number of arguments.

## Input/Output
### `print`
Syntax: `print(str: str)`.

Prints `str` in console. Returns None. Example: `print("hello, world!")`.

### `print_ret`
Syntax: `print_ret(str: str)`.

Prints `str` in console and returns it. Example: `print_ret("hello, world!")`.

### `print_in_red`
Syntax: `print_in_red(str: str)`.

Prints str in red in console. Returns None. Example: `print_in_red("Error: this error is RED")`.

### `print_in_red_ret`
Syntax: `print_in_red_ret(str: str)`.

Prints str in red in console and returns it. Example: `print_in_red_ret("Error: this error is RED and returned")`

### `print_in_green`
Syntax: `print_in_green(str: str)`.

Prints str in green in console. Returns None. Example: `print_in_green("Info: this info is GREEN")`.

### `print_in_green_ret`
Syntax: `print_in_green_ret(str: str)`.

Prints str in green in console and returns it. Example: `print_in_green_ret("Info: this info is GREEN and returned")`

### `input`
Syntax: `input(<text_to_display: str = "">)`.

Inputs a str. If `text_to_display` is specified, it is printed as a prompt.

### `input_int`
Syntax: `input_int(<text_to_display: str = "">)`.

Inputs an int. If `text_to_display` is specified, it is printed as a prompt.

### `input_num`
Syntax: `input_num(<text_to_display: str = "">)`.

Inputs an int or a float. If `text_to_display` is specified, it is printed as a prompt.

## Types
!!! note
    Python `isinstance()` returns `True` if `value` is an object of the given type.

### `type`
Syntax: `type(value: Any)`

Returns a str of the internal type of the value. It can be `str`, `int`, `float`, `list`, `func`, `module`, ...

### `is_int`
Syntax: `is_int(value: Any)`

Returns `True` if `value` is an [integer](../Language/06values.md#numbers), `False` if it is not. Corresponds to `isinstance(value, int)`.

### `is_float`
Syntax: `is_float(value: Any)`

Returns `True` if `value` is a [float](../Language/06values.md#numbers), `False` if it is not. Corresponds to `isinstance(value, float)`.

### `is_num`
Syntax: `is_num(value: Any)`

Returns `True` if `value` is a [number](../Language/06values.md#numbers), `False` if it is not. Corresponds to `isinstance(value, float) or isinstance(value, int)`.

### `is_str`
Syntax: `is_str(value: Any)`

Returns `True` if `value` is a [string](../Language/06values.md#strings), `False` if it is not. Corresponds to `isinstance(value, str)`.

### `is_list`
Syntax: `is_list(value: Any)`

Returns `True` if `value` is a [list](../Language/06values.md#lists), `False` if it is not. Corresponds to `isinstance(value, list)`.

### `is_func`
Syntax: `is_func(value: Any)`

Returns `True` if `value` is a [function](../Language/10functions.md), `False` if it is not. Corresponds to `isinstance(value, BaseFunction)` where `BaseFunction` is function, method and builtin function.

### `is_module`
Syntax: `is_module(value: Any)`

Returns `True` if `value` is a [module](../Language/06values.md#modules), `False` if it is not. Corresponds to `isinstance(value, module)`. Example: `import math; is_module(math)` will be `True`, but `is_module(3.2)` will be `False`.

### `is_none`
Syntax: `is_none(value: Any)`

Returns `True` if `value` is [`None`](../Language/06values.md#none), `False` if it is not. Corresponds to `isinstance(value, NoneValue)` or `value is None`.

### `is_constructor`
!!! info ""
    Added in 0.20.0-beta

Syntax: `is_constructor(value: Any)`

Returns `True` if `value` is a [constructor](../Language/12classes.md#constructor-value), `False` if it is not. Corresponds to `isinstance(value, Constructor)`.

### `is_object`
!!! info ""
    Added in 0.20.0-beta

Syntax: `is_object(value: Any)`

Returns `True` if `value` is an [object](../Language/12classes.md#object), `False` if it is not. Corresponds to `isinstance(value, object)`. Note: in Nougaro, everything is not an object!

## Type conversions
### `str`
Syntax: `str(value: Any)`

Converts value to [string](../Language/06values.md#strings) (may return an error).

### `int`
Syntax: `int(value: Any)`

Converts value to [int](../Language/06values.md#numbers) (may return an error).

### `float`
Syntax: `float(value: Any)`

Converts value to [float](../Language/06values.md#numbers) (may return an error).
Note that `float("inf")` is infinity and `float("nan")` is not a number.

### `list`
Syntax: `list(value: Any)`

Converts value to [list](../Language/06values.md#lists) (may return an error).

## String and lists operators
### `upper`
Syntax: `upper(value: str)`

Returns upper-cased string. Example: `upper('nougaro')` returns `'NOUGARO'`.

### `lower`
Syntax: `lower(value: str)`

Returns lower-cased string. Example: `lower('NOUGARO')` returns `'nougaro'`.

### `split`
Syntax: `split(value: str, <char: str = " ">)`

Returns splitted string. For example, `split('a b c')` returns `['a', 'b', 'c']` ; `split('a b c', 'b')` returns `['a ', ' c']`.

### `startswith`
Syntax: `startswith(value: str, substring: str)`

Returns True if `value` starts with `substring`. Example: `"nougaro"` starts with `"noug"`, but `"canal du midi"` does not start with `"minimes"`.

### `endswith`
Syntax: `endswith(value: str, substring: str)`

Returns True if `value` ends with `substring`. Example: `"nougaro"` ends with `"garo"`, but `"canal du midi"` does not end with `"minimes"`.

### `len`
Syntax: `len(value: list | str)`

Returns the number of elements in a list (i.e. its length), or the number of chars in a str.

### `reverse`
Syntax: `reverse(value: list | str)`

Reverses list or string `value` by reference and returns the result. Example: `reverse([1, 2, 3])` is `[3, 2, 1]`.

### `append`
Syntax: `append(list: list, value: Any)`

Appends value at the end of the list. Returns a list. If the list is a variable, edits the variable.

### `pop`
Syntax: `pop(list: list, <index: int = -1>)`:

Deletes value at given index. Returns the popped element. If the list is a variable, edits the variable. If `index` is not given, the last element of the list is popped.

### `insert`
Syntax: `insert(list: list, value: Any, <index: int = -1>)`

Inserts value at the given index in the list.

### `replace`
Syntax: `replace(list: list, index: int, value: Any)`

Replaces value at the given index in the list.

### `extend`
Syntax: `extend(list1: list, list2: list, <remove_duplicates: int = False>)`

Appends to `list1` the elements of `list2`. Returns `list1`. If `list1` is a variable, edits the variable. If `remove_duplicates` is True, removes the `list2` elements already in `list1` before extending.

### `get`
Syntax: `get(list: list, index: int)`

Returns the element of the list at the given index.

### `max`
Syntax: `max(list: list, <ignore_not_num: int = False>)`

Returns the maximum element of the list. Ignores elements that are not numbers if `ignore_not_num` is `True`, otherwise crashes if such element exists.

### `min`
Syntax: `min(list: list, <ignore_not_num: int = False>)`

Returns the minimum element of the list. Ignores elements that are not numbers if `ignore_not_num` is `True`, otherwise crashes if such element exists.

### `sort`
Syntax: `sort(value: list, <mode: str = "timsort">)`

!!! note
    * Slowsort and bogosort were added in 1.2.0

Sorts list `value` according to mode `mode`. Lefts the original list unchanged
and returns a new list.
Available modes are: `timsort` (default), `miracle`, `panic`, `sleep`, `slow`
and `stalin`.

* `timsort` is Python’s default algorithm
* [`bogo`sort](https://en.wikipedia.org/Bogosort) randomly shuffles the list
  until it is sorted. May take an infinite amount of time!
* `miracle`sort literally waits for a miracle. It checks if the list is sorted,
  and if it is not, it checks again. If a cosmic ray (or
  [another miracle](../../miraclesort.webm)) flips the right bits in your RAM
  so the list is sorted, miraclesort will return the sorted list.
* `panic`sort checks if the list is sorted. If so, it returns it. If the list
  is not sorted, this causes an illegal hardware instruction (Unix and
  GNU/Linux) or a segfault (Windows).
* `sleep`sort take only a list of positive integers. It starts as many threads
  as elements in the list, and each thread waits for as much seconds as the
  element. For instance, when the list `[5, 2, 3, 0]` is passed in sleepsort,
  it starts by launching 4 threads that wait for 5, 2, 3 and 0 seconds. When a
  thread finishes to wait, it append its element to the list. Use the mode
  `sleep-verbose` to see what’s happening.
* `slow`sort really sorts the list, but is very slow (even the best case is
  worst than bubble sort). See
  [the wikipedia page](https://en.wikipedia.org/Slowsort) about slowsort.
* `stalin` sends to gulag values that are not sorted (i.e. pop them from the
  list). Example: `[1, 4, 3, 7, 6, 10, 2, 5, 23]` will be sorted as
  `[1, 4, 7, 10, 23]`.

## Number operators
### `round`
Syntax: `round(number: int | float, <n_digits: int = 0>)`

Rounds `number` to the closest number with `n_digits` decimals. `n_digits` may be 0 or negative, in which case the returned type is `int`.

!!! info "Changed in 0.22.0-beta"
    The `round` built-in function previously returned `int` only when `n_digits` was 0 (now it is the case when `n_digits` ⩽ 0)

## Characters and Unicode
!!! note
    There’s more in the [`unicodedata`](modules/unicodedata.md) module.

### `ord`
Syntax: `ord(c: str)`

Returns an integer representing the Unicode code point of that `c`. `c` is a string with only one character. Ex: `ord('a')` returns `97` and `ord('€')` returns `8364`.

### `chr`
Syntax: `chr(i: int)`

Returns the string representing the character whose Unicode code point is the integer `i`. For example, `chr(97)` returns the string `'a'`, and `chr(8364)` returns the string `'€'`.

## License
### `__gpl__`
Syntax: `__gpl__(<print_in_term: int = False>)`

If `print_in_term` is `True`, prints the General Public License 3.0 in the terminal. Otherwise, it opens the GPL in the default system program.

## Files
### `__path_exists__`
Syntax: `path_exists(path: str)`

Returns `True` (`1`) if the path exists, `False` (`0`) otherwise.

## Technical
### `exit`
Syntax: `exit(<stop_code: int | str = 0>)`

Just quits the interpreter.

### `clear`
Syntax: `clear()`

Clears the screen. Returns [`None`](../Language/06values.md#none).

### `void`
Syntax: `void(*args)`

Does nothing. Returns [`None`](../Language/06values.md#none).

### `run`
Syntax: `run(file_name: str)`

Executes the code in the file `file_name`.

### `example`
Syntax: `example(<example_name: str | None = None>, <return_example_value: int = False>)`

Executes the code in the file `examples/(example_name).noug`. If `example_name` is `None`, executes the code in the file `example.noug`.

If `return_example_value` is `True`, returns the list value from the example execution.

### `system_call`
!!! warning
    This function may be dangerous, because *any* system command can be executed.

Syntax: `system_call(cmd: str)`

Calls `cmd`. Prints the result of the command and returnt the stop code as [str](../Language/06values.md#strings).

### `__python__`
!!! warning
    This function may be dangerous, because *any* Python code can be executed.

Syntax: `__python__(source: str)`

Runs Python’s `eval(source)`.

### `__is_keyword__`
Syntax: `__is_keyword__(word: str)`

Check if `word` is a valid Nougaro [keyword](../Language/04identifiers_and_keywords.md#keywords).

### `__is_valid_token_type__`
Syntax: `__is_valid_token_type__(tok_type: str)`

Checks if `tok_type` is a valid Nougaro token type, such as 'EE' or 'BITWISENOT'.

### `__test__`
Syntax: `__test__(<should_print_ok: int = False>, <should_i_return: int = False>)`

Executes the test file for the Nougaro interpreter. If `should_print_ok` is `True`, prints “OK” each times a test was succesful. If `should_i_return` is true, returns the value of the interpreted file.

### `__py_type__`
Syntax: `__py_type__(value)`

Returns the string of Python’s `type(value)`. For instance, `__py_type__(__py_type__)` is `"<class 'src.runtime.values.functions.builtin_function.BuiltInFunction'>"`

### `__how_many_lines_of_code__`
Syntax: `__how_many_lines_of_code__(<print_details: Any = True>)`

Lets you know how many lines of code there are in Nougaro. If `print_details` is True, details how many lines of code they are in each file.

## Mathematical functions
Please refer to [Math module](modules/math.md).
