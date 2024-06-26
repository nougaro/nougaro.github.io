# List of built-in variables

## Useful ones
### `__args__`
!!! note
    Added in 0.16.0-beta

List of the command line arguments (type string).

Examples (assuming your Nougaro command is `noug`):
* `noug -c "print(__args__)" -t d 78876876 -v tth` prints `["-c", "-t", "d", "78876876", "-v", "tth"]`
* `noug examples/args.noug -t d 78876876 -v tth` prints `["examples/args.noug", "-t", "d", "78876876", "-v", "tth"]` (check out the contents of `args.noug`)
* `noug -c "print(__args__)"` prints `["-c"]`
* entering the shell then entering `print(__args__)` prints `[]`

## Nougaro informations
!!! note
    This section is duplicated in [this file](../internals.md)

* `__noug_version__`: string of the Nougaro version (e.g. "0.15.0-beta".) You can use the [`noug_version`](modules/noug_version.md) lib to have better informations.
* `__data_version__`: the Nougaro data version, an internal version keeping track of changes in the config file directory structure
* `__version_id__`: an ID increased at least once per version
* `__python_version__`: string of the Python version (e.g. "3.10.5")
* `__noug_dir__`: string of the absolute path of the directory where shell.(py/exe) is located. May be used with file I/O `read` and `write` statements.

## OS informations
* `__os_name__` : name of the Operating System (e.g. "Windows", "Linux", "Darwin" –&nbsp;for macOS&nbsp;–, "Java" –&nbsp;for Jython&nbsp;–, …)
* `__os_release__` : release of the OS (e.g. "10" for Windows 10, "Vista" for Windows Vista.)
* `__os_version__` : version of the OS (e.g. "10.0.19044" for Windows 10 build 19044.)

# Examples
```
print("You use Nougaro version " + __noug_version__ + ", interpreted with Python " + __python_version__)
print("You use " + __os_name__ + " " + __os_release__ + " " + __os_version__)
```
On the Jean Dubois' old computer, under Windows 10 21H2, it returns:
```
You use Nougaro version alpha 0.8.1, interpreted with Python 3.10.5
You use Windows 10 10.0.19044
```
And under his Linux:
```
You use nougaro version beta 0.14, interpreted with Python 3.11.4
You use Linux 6.2.0-27-generic #28-Ubuntu SMP PREEMPT_DYNAMIC Wed Jul 12 22:39:51 UTC 2023
```

Note that this code is in [example.noug](https://github.com/jd-develop/nougaro/blob/main/example.noug)
