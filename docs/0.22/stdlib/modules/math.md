# `math` module

The `math` module can be imported with the statement `import math`.

The `math` module is used to do math. To do statistics, use the [`statistics`](statistics.md) module.

# Constants
* `math.pi`: [Pi](https://en.wikipedia.org/wiki/Pi). $\pi = 3.141592653589793$
* `math.tau`: [Tau](https://tauday.com/). $\tau = 6.283185307179586$
* `math.sqrt_pi`: square root of pi (`math.sqrt(math.pi)`). $\sqrt\pi = 1.7724538509055159$
* `math.sqrt_tau`: square root of tau (`math.sqrt(math.tau)`). $\sqrt\tau = 2.5066282746310002$
* `math.e`: [Euler's number](https://en.wikipedia.org/wiki/E_(mathematical_constant)). $e = 2.718281828459045$

# Functions
### `math.sqrt`
Syntax: `math.sqrt(n)`

Returns $\sqrt{n}$ (square root of $n$), $n \in \mathbb{R}_+$

### `math.isqrt`

Syntax: `math.isqrt(n)`

Returns $\left\lfloor\sqrt{n}\right\rfloor$ (integer square root of $n$), $n \in \mathbb{N}$

### `math.root`

Syntax: `math.root(n, k)`

Returns the $\sqrt[k]{n}$ ($k$-th root of $n$), $n \in \mathbb{R}_+, k \in \mathbb{R}$

### `math.iroot`

Syntax: `math.iroot(n, k)`

Returns $\left\lfloor\sqrt[k]{n}\right\rfloor$ (integer $k$-th root of $n$), $n \in \mathbb{R}_+, k \in \mathbb{R}$

### `math.degrees`

Syntax: `math.degrees(angle)`

Transforms a radian angle to a degree angle. $\verb|angle| \in \mathbb{R}$

### `math.radians`

Syntax: `math.radians(angle)`

Transform a degree angle to a radian angle. $\verb|angle| \in \mathbb{R}$

### `math.sin`

Syntax: `math.sin(angle)`

Returns sine of an angle in radians. $\verb|angle| \in \mathbb{R}$

### `math.cos`

Syntax: `math.cos(angle)`

Returns cosine of an angle in radians. $\verb|angle| \in \mathbb{R}$

### `math.tan`

Syntax: `math.tan(angle)`

Returns tangent of an angle in radians. $\verb|angle| \in \mathbb{R}$

### `math.asin`

Syntax: `math.asin(sin)`

Returns arcsine of an sin (result in radians). $\verb|sin| \in [-1, 1]$

### `math.acos`

Syntax: `math.acos(cos)`

Returns arccosine of an cos (result in radians). $\verb|cos| \in [-1, 1]$

### `math.atan`

Syntax: `math.atan(tan)`

Returns arctangent of an tan (result in radians). $\verb|tan| \in \mathbb{R}$

### `math.abs`

Syntax: `math.abs(n)`

Returns $\left|n\right|$ (absolute value of $n$), $n \in \mathbb{R}$

### `math.log`

Syntax: `math.log(n, <base>)`

Returns the natural logarithm (`base`=$e$) of $n$ if no base is given, or the logarithm of $n$ in the given base. $n, base \in \mathbb{R}$

### `math.log2`

Syntax: `math.log2(n)`

Same as `math.log(n, 2)`. $n \in \mathbb{R}$

### `math.factorial`

!!! note ""
    Added in 0.19.0-beta

Syntax: `math.factorial(n)`

Returns $n!$ ([factorial](https://en.wikipedia.org/wiki/Factorial) of $n$). $n \in \mathbb{N}$
