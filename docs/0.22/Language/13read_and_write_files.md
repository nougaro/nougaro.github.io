# Read and write in files

## Read
To read a file, use `read "path/to/file.ext"` or `read "path/to/file" line_number`. You can assign this value to a variable by using `read "file" >> identifier line_number` or `var identifier = read "file" line_number`. `line_number` is an [integer](06values.md#numbers) and is optional.

You can use `"<stdin>"` as file name to get a line of input from the user. It is exactly like the [`input` built-in function](../stdlib/02builtin-functions.md#input).

The `read` expression returns the content of the file (or of the line).

## Write
To write in a file, use `write "sometext" >> "path/to/file.ext" line_number`. `line_number` is an integer and is optional.

To overwrite the content when you write, replace `>>` by `!>>`.

You can use `"<stdout>"` as file name to print a text in the console. It is exactly like the [`print` built-in function](../stdlib/02builtin-functions.md#print). If you overwrite the contents of `<stdout>`, the console is cleared (exactly like the [`clear` built-in function](../stdlib/02builtin-functions.md#clear).)

The `write` expression returns the text that was wrote in the file.
