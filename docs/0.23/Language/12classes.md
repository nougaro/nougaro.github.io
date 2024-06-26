# Classes and objects

!!! note
    Added in 0.15-beta

Nougaro is an object-oriented programming language, which means you can create objects using **classes**.

## Class definition

To define a class, use this syntax:
```nougaro
class Name
    ...
end
```

To create [attributes](11attributes.md), just use the basic `var id = value` syntax:
```nougaro
class Name
    var a = 3
    var b = 1
end
```

To create [methods](#methods), just use the basic [`def` syntax](10functions.md#definition). Access to object’s [attributes](11attributes.md) with `this`:
```nougaro
class Name
    var a = 3
    var b = 1

    def increment_b(by)
        var this.b += 1
    end

    def get_a()
        return this.a
    end
end
```

Methods are [attributes](11attributes.md) themselves.

### Methods

Internal type: `method`.

No [operation](05operators.md) can be used on methods.

Methods are true in boolean context.

!!! note "Changed in 0.22.0-beta"
    Prior to 0.22.0-beta, methods were false in boolean context.

### Constructor value

Internal type: `constructor`.

No [operation](05operators.md) can be used on constructors.

Constructors are false in boolean context.

### Inheritance

To inherit from another class, use the `class Name(Iherit)` syntax:
```nougaro
class ChildOfName(Name)
    var c = 3

    def set_c(new_value)
        var this.c = new_value
    end

    def a_plus_b_plus_c()
        return this.get_a() + this.b + this.c
    end
end
```

## Object

Classes can be instanced into objects by calling them.

Example:
```nougaro
var instance = Name()

instance.increment_b(10)
assert instance.b == 11
```

Internal type: `Name` (depends on the class’ name).

No [operation](05operators.md) can be used on objects.

Objects are false in boolean context.

## Example
See the `stack.noug` example located in `./examples/` in the main Nougaro repository.
