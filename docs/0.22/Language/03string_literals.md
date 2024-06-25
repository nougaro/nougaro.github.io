# String literals

String literals are delimited by `""`, `''` or `«»`.

Examples:
```nougaro
"hello"
'hello'
«hello»
```

Escape characters:

* `\'`         :  '
* `\"`         :  "
* `\»`         :  »
* `\n`         :  backline
* `\t`         :  tab
* `\\`         :  backslash
* `\xAA`       :  unicode character number AA (hex)
* `\uAAAA`     :  unicode character number AAAA (hex)
* `\UAAAAAAAA` :  unicode character number AAAAAAAA (hex)
* `\N{NAME}`   :  unicode character with name NAME. Returns `SyntaxError` if it doesn’t exist.

!!! note
    The backslash isn’t left if the next character is not recognised (example: `"\/"` is the same as `"/"`, and not `"\\/"`)

Examples:
```nougaro
'I\'m a string literal'
"He said: \"'I'm a string literal'\""
"\\ backslashes, \t tabs and \n backlines"
«This string has a \N{NO BREAK SPACE}»
"\N{Latin Small Letter C with Cedilla}: \xe7"
"\N{Greek Small Letter Eta with Dasia and Oxia and Ypogegrammeni}: \u1F95"
"This is Person Shrugging (🤷): \U0001f937"
```

!!! note
    You can use the [meta](14metas.md) `nbspBetweenFrenchGuillemets` to be forced to use a no-break-space or a narrow-no-break-space after `«` and before `»`. These NBSP are not counted in the string and this does not affect the other string delimiters.
