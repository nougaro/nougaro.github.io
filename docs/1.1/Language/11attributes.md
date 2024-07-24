# Attributes

[Values](06values.md) in Nougaro can have attributes, i.e. subvalues that have a name.

They can be set using the classical [variable definition](07variables.md) syntax:
```nougaro
var variable.attribute = value
```

They can be accessed using the dot-syntax:
```nougaro
variable.attribute
```

!!! note
    You can even access any name defined in the context of the value. For instance, `variable.print` references the [`print`](../stdlib/02builtin-functions.md#print) built-in function.

    !!! info "Pro tip"
        The next time you have a bug, document it. If it is documented, it is therefore not a bug.
