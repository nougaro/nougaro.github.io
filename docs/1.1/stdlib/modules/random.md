# Random

*[Source code](https://github.com/jd-develop/nougaro/blob/main/lib_/random_.py)*

The `random` module can be imported with the statement `import random`.

The `random` module is used to generate random numbers.

## Functions
### `random.randint`

Syntax: `random.randint(a: int, b: int)`

Generates a random integer between `a` and `b`. `a` and `b` must be [integers](../../Language/06values.md#numbers). The [condition](../../Language/08tests.md#conditions) `a <= b` MUST be verified.

### `random.random`

Syntax: `random.random`

Generates a random floating number between 0.0000000000000000 and 1.0000000000000000.

### `random.choice`

Syntax: `random.choice(list)`

Returns a random element of the `list`.

### `random.shuffle`

Syntax: `random.shuffle(list)`

Shuffles (by reference) and returns `list`.

### `random.seed`

Syntax: `random.seed(int)`

Sets the seed to generate numbers to `int`.
