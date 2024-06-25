# Import and export

`import` and `export` are two [keywords](04identifiers_and_keywords.md#keywords) related to [modules](06values.md#modules)/libraries.

## Import
The `import` keyword is used to import a module in the current code. It follows the syntax `import name` or `import name as alias`. It checks for `name` in Nougaro [stardard library](../stdlib/modules/index.md) and in the current directory for a file named `name.noug`. `dir.subdir.name` looks for `./dir/subdir/name.noug`. Note: the current directory is the directory of the file that were executed. For instance, if the file `foo.noug` (in the directory `project`) imported `dir.bar`, and that `dir/bar.noug` has `import name`, name is checked in the `project` directory.

The `import` keyword created a [module](06values.md#modules) value with, as attributes, all the values exported by the module.

## Export
The `export` keyword is used to export a value in a module, that will become an attribute of the module’s value when imported.
It follows the syntax `export name` or `export expression as name`.
More in [this page](../Expanding/Write-libs.md).
