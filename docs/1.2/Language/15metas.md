# Metas
!!! note
    Added in 0.19.0-beta

Metas are a way to use other (or old) functionnalities in Nougaro.
They’re used by adding `@meta metaName` or `@meta metaName value` at the beginning of a file or in an interactive shell.
Note that, instead of `@`, you can use any of those prefixes: `#@`, `%@`, `@@`, `-@`, `$@`.

!!! important
    `value` should only be composed of ASCII upper- and lowercase letters.

## `appendNoneOnBreak`
!!! note
    Added in 0.20.0-beta

If enabled, this meta forces a [`break`](09loops.md#break-continue) statement to append [`None`](06values.md#none) to the [list](06values.md#lists) returned by the [loop](09loops.md).


## `appendNoneOnContinue`
!!! note
    Added in 0.20.0-beta

If enabled, this meta forces a [`continue`](09loops.md#break-continue) statement to append [`None`](06values.md#none) to the [list](06values.md#lists) returned by the [loop](09loops.md).

## `legacyAbs`
The `legacyAbs` meta lets you use the old syntax (in the `prototype-1` version) for absolute value, which is `|...|`. However, this meta disables the bitwise or [operation](05operators.md).

Example:
```nougaro
@meta legacyAbs
print(|-1|)  # 1
var a = 12
print(|-a|)  # 12
```

## `nbspBetweenFrenchGuillemets`
The `nbspBetweenFrenchGuillemets` meta requires you, if you use the french [string](03string_literals.md) quotes (`«»`), to put a no-break space (or a narrow no-break space) after the `«` and before the `»`.

Example:
```nougaro
@meta nbspBetweenFrenchGuillemets
print(« hello, world »)  /* hello, world
                          * note that the quotes aren’t regular spaces
                          */
```

## `setTheTestValueTo`
* Sets `__the_test_value__` to the [str](06values.md#strings) value given in the meta value
* If no value is given, it sets it to [`None`](06values.md#none).
