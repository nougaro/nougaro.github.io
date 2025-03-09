You are a Nougaro developer, and you want to write an amazing library to implement python amazing things in Nougaro? You're at the right place!!

You have to options: either [writting it in Nougaro](#write-libs-in-nougaro) (with limited resources), either [writting it in Python](#write-libs-in-python) (with [unlimited](https://xkcd.com/353/) resources).

# Write libs in Nougaro
## Requirements
You need to know how to code in Nougaro.

## Start coding
The file should be named `nameofthelib.noug` and be located in the `lib_` folder in the Nougaro repository.

Simply write all your code. If you want something to be accessible when imported, **use one of those syntaxes**:

* `export identifier (as identifier)`
* `export (any expression) as identifier`

You can find examples of built-in modules written in Nougaro in the `lib_` folder.

# Write libs in Python
!!! Warning
    Everything changed in 0.16.0-beta and in 0.19.0-beta

## Requirements
You need to know how to code in Python. Don't worry, that's easy ;)

## Start coding
The file should be named `nameofthelib_.py` (the “\_” is VERY important!!)
The file will be placed in the `lib_` folder in the Nougaro repository.

Paste this generic code in your file:
```python
# -*- coding:utf-8 -*-
""" YourModuleName module

    YourModuleName is a module that do [...] and [...] and also [...].
"""
# IMPORTS
# nougaro modules imports
from lib_.lib_to_make_libs import *  # useful stuff to make libs.
# built-in python imports
# here put the useful python imports your module will need ;)

__LIB_VERSION__ = 4
```

!!! note
    Lib versions depending on Nougaro versions:

    * prior to 0.20.0: `1`
    * 0.20.0: `2`
    * 0.21.0: `3`
    * since 0.22.0: `4`

### Lib with constants
If your lib contains constants, you can add them to the code, outside any class.

Use `py2noug` function imported from `lib_to_make_libs` to convert Python values to Nougaro values.

Python types that can be converted into Nougaro values are: `str`, `int`, `float`, `bool` (which is converted to 0 or 1), `list`, `tuple` (converted into list), `dict` (converted into a list of lists, each sub-list is `[key, value]`), `None`. Other types will return generic value `Value`, which you can't make anything with...

Example:
```python
AMAZING_CONSTANT = py2noug(3, *default_pos())   # will be Number(3), type 'int'
ANOTHER_AMAZING_CONSTANT = py2noug("Hello world :)", *default_pos())  # will be String("Hello world :)"), type 'str'
```

(`py2noug` and `default_pos` are imported from `lib_to_make_libs`)

### Lib with functions
If you want functions in your lib, paste this code in your file (replace the
generic names/texts with appropriate things, except for `function_name`, as
the class is actually a wrapper for all the functions in your module):
```python
class YourModuleName(ModuleFunction):
    """ YourModuleName Module """
    functions: dict[str, builtin_function_dict] = {}

    def __init__(self, function_name: str):
        super().__init__("your_module_name", function_name, "https://link_to_report_bugs.com (not required)", functions=self.functions)

    def copy(self):
        """Return a copy of self"""
        copy = YourModuleName(self.name)
        return self.set_context_and_pos_to_a_copy(copy)

    def is_eq(self, other: Value):
        return isinstance(other, YourModuleName) and self.name == other.name
```

!!! note "Changed in 0.20.0-beta"
    Prior to 0.20.0, the method `is_eq` was named `get_comparison_eq` and had this syntax:
    
        def get_comparison_eq(self, other: Value):
            if isinstance(other, YourModuleName):
                return Number(self.name == other.name, self.pos_start, other.pos_end).set_context(self.context), None
            return Number(False, self.pos_start, other.pos_end).set_context(self.context), None

Then, to add a function, add a method in this class following this syntax:

```python
    def execute_function_name(self, context: Context):
        """ Docstring (optional) """
        assert context.symbol_table is not None
        ...
    
    functions["function_name"] = {
        "function": execute_function_name,
        "param_names": ["parameter_1", "parameter_2"],
        "optional_params": ["optional_parameter_1"],
        "should_respect_args_number": True,
        # The two following values are used internally.
        # They are not documented, don’t set them to True except if you know what you’re doing.
        "run_noug_dir": False,
        "noug_dir": False
    }
```

!!! Note "Changed in 0.22.0-beta"
    Prior to 0.22.0-beta, the key `"run_noug_dir"` was called `"run_noug_dir_work_dir"`.

* keys `param_names` and `optional_params` should be of type `list[str]`.
* `should_respect_args_number` is a bool. It is `True` when the number of given arguments should match with the number of parameters, and `False` if not.

You can then add code in your function.

### Get arguments
To get the arguments given by the user in your functions, use
```python
    context.symbol_table.getf("identifier")
```
Replace the identifier by the one you given to the parameter.

If your parameter is optional and that the user didn’t specified it, the default value is a Python `None` (not a Nougaro `NoneValue`).

!!! danger
    Please don’t use `.get` symbol table method, it does NOT work in modules (even if it looks like) and should NOT be used. (The short explanation why is that this method looks for the name also in parent symbol table, so if an optional param is not given but the user defined a variable with that name, it will be taken as the value for that param, which is not what we want. We don’t care about parent symbol table, so we just look in the current symbol table which only contains the parameters. The corresponding issue is [#10](https://github.com/jd-develop/nougaro/issues/10).)

### Values
!!! warning "Important"
    You often have to switch between Nougaro and Python values! To convert python to Nougaro values, use `py2noug` function. To convert Nougaro to python values, use `noug2py`. Both functions are imported from `lib_to_make_libs`. You reed a position with `py2noug`: you can simply put `self.pos_start` and `self.pos_end` or the position of any value you want.

### What to return? Values and errors.
If you don't need to return anything, simply use `return RTResult().success(NoneValue(*default_pos(), False))`.

#### Return errors
Oops! It crashed! How to say it to the user under a good shape?
Simply use this syntax:
```python
    return RTResult().failure(NameOfTheError(
        self.pos_start, self.pos_end,
        "error message.",
        context
    ))
```

If the user gave you a value with an incorrect type, use:
```python
    return RTResult().failure(RTTypeErrorF(
        bad_argument.pos_start, bad_argument.pos_end,
        "first/second/third…", "name of the module.name of the function", "type that should be found", bad_argument,
        context
    ))
```
Replace `"first/second/third…"` by the actual index of the argument. If it is the first argument, put `"first"`, et cætera. The error will print, for instance, `second argument of builtin function 'name of the function' should be 'type that should be found', not 'type of (bad_argument)'.`

You can replace `self` by any Nougaro value, such as your arguments.

For example, in the lib `math`:
```python
    if value.value < 0:  # we check if the value is greater than (or equal to) 0
        return RTResult().failure(RTArithmeticError(
            value.pos_start, value.pos_end,
            "first argument of the built-in function 'math.sqrt' must be greater than (or equal to) 0.",
            exec_context, "lib_.math_.Math.execute_math_sqrt"
        ))
```

All the errors available in a Module:

* `RunTimeError`: basic run-time error
* `RTIndexError`: IndexError
* `RTArithmeticError`: ArithmeticError
* `RTNotDefinedError`: NotDefinedError
* `RTTypeErrorF`: TypeError (you give a Number but you need a String)
* `RTFileNotFoundError`: FileNotFoundError
* `RTAssertionError`: AssertionError (not useful in libs...)
* `RTAttributeError`: AttributeError
* `RTOverflowError`: OverflowError
* `RTRecursionError`: RecursionError (new in 0.20.0)
* `PythonError`: PythonError: an error due to Python. Don’t put a str error message: pass directly the Python Exception.

#### Return values
To return a *Nougaro* value, use
```python
return RTResult().success(value)
```

To return a *Python* value, use
```python
return RTResult().success(py2noug(value, self.pos_start, self.pos_end))
```

## `WHAT_TO_IMPORT` : DO NOT forget that one!!
When you have finished coding your amazing lib, create the `WHAT_TO_IMPORT` dict. It tells to the Nougaro Interpreter what should be imported and with which name. Follow this syntax:
```python
WHAT_TO_IMPORT = {
    "name_of_a_constant": IDENTIFIER,
    "name_of_a_function": YourModuleName('function_name'),
}
```
The function name is what you specified as the key of the `functions` dictionary.

## Custom errors
To use a custom error in your code, simply copy-paste this code:
```python
class YourErrorName(RunTimeError):
    """YourErrorName is an error that can be triggered ONLY via functions in this module."""
    def __init__(self, pos_start: Position, pos_end: Position, details: str, context: Context, origin_file: str = "lib_.(nameofthelib)_"):
        super().__init__(pos_start, pos_end, details, context, rt_error=False, error_name="YourErrorName", origin_file=origin_file)
```

Then, call it like any other errors (like [this](https://github.com/jd-develop/nougaro/wiki/Write-libs#what-to-return-values-and-errors))

Note: `origin_file` is used for debugging. To trigger it, you can run:

```nougaroshell
nougaro> import debug;debug.enable()
DEBUG mode is now ENABLED.
[<module debug>, None]
nougaro> (anything that throws an error)
```

Example:

```nougaroshell
nougaro> import debug;debug.enable()
DEBUG mode is now ENABLED.
[<module debug>, None]
nougaro> thisisnotdefined
[identifier:"thisisnotdefined", end of file]
list:[(var_access:[identifier:"thisisnotdefined"], False)]
(from src.runtime.interpreter.Interpreter.visit_VarAccessNode (is NOT lib and close match in symbol table))
Traceback (most recent call last):
 In file <stdin>, line 1, in <program>:

        thisisnotdefined
        ^^^^^^^^^^^^^^^^
 NotDefinedError: name 'thisisnotdefined' is not defined. Did you mean 'is_none'?
nougaro> this is a syntax error
[identifier:"this", identifier:"is", identifier:"a", identifier:"syntax", identifier:"error", end of file]
(from src.parser.parser.Parser.statements)
In file <stdin>, line 1: 
        this is a syntax error
             ^^
 InvalidSyntaxError: unexpected token: identifier:"is".
nougaro>
```

Here, `origin_file` is `src.runtime.interpreter.Interpreter.visit_VarAccessNode` and `src.parser.parser.Parser.parse`.

### Example: `RTStatisticsError` in built-in lib `statistics`
```python
class RTStatisticsError(RunTimeError):
    """StatisticsError is an error that can be triggered ONLY via functions in this module."""
    def __init__(self, pos_start: Position, pos_end: Position, details: str, context: Context,
                 origin_file: str = "lib_.statistics_"):
        super().__init__(pos_start, pos_end, details, context, rt_error=False, error_name="StatisticsError",
                         origin_file=origin_file)
```

## Examples
You can read builtin files stored in `lib_` folder to make you a good idea of what a nice-coded lib is ;)

## Here you go!
If you think that your lib is absolutely awesome, you can open a [PR](https://github.com/jd-develop/nougaro/pulls) to submit your idea. The best ideas will be implemented into vanilla Nougaro! If you think that this document is incomplete, that it didn’t help you, or just to find some help, open an [issue](https://github.com/nougaro/nougaro.github.io/issues/new).
