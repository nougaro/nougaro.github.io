# Statistics

*[Source code](https://github.com/jd-develop/nougaro/blob/main/lib_/statistics_.py)*

The `statistics` module can be imported with the statement `import statistics`.

The `statistics` module is used to do statistics. To do math, use the [`math`](math.md) module.

## Functions
### `statistics.mean`

Syntax: `statistics.mean(list)`

Calculates the mean of a list of numbers. 

### `statistics.geometric_mean`

Syntax: `statistics.geometric_mean(list)`

Calculates the geometric mean of a list of positive numbers.

### `statistics.harmonic_mean`

Syntax: `statistics.harmonic_mean`

Calculates the harmonic mean of a list of positive numbers.

### `statistics.median`

Syntax: `statistics.median(list)`

Calculates the median of a list of numbers.

### `statistics.quantiles`

Syntax: `statistics.quantiles(list, n=4, method='exclusive')`

Cuts a list of numbers in `n` parts and returns a list of the values where the list was cut, using `exclusive` or `inclusive` method. `n` and `method` are optional.

!!! warning "Disclamer from the [Python source code](https://github.com/python/cpython/blob/769aea332940f03c3e5b1ad9badd6635c1ac992a/Lib/statistics.py#L1121)"
    Notes on methods for computing quantiles
    ----------------------------------------
    
    There is no one perfect way to compute quantiles.  Here we offer
    two methods that serve common needs.  Most other packages
    surveyed offered at least one or both of these two, making them
    "standard" in the sense of "widely-adopted and reproducible".
    They are also easy to explain, easy to compute manually, and have
    straight-forward interpretations that aren't surprising.

    The default method is known as "R6", "PERCENTILE.EXC", or "expected
    value of rank order statistics". The alternative method is known as
    "R7", "PERCENTILE.INC", or "mode of rank order statistics".

    For sample data where there is a positive probability for values
    beyond the range of the data, the R6 exclusive method is a
    reasonable choice.  Consider a random sample of nine values from a
    population with a uniform distribution from 0.0 to 1.0.  The
    distribution of the third ranked sample point is described by
    betavariate(alpha=3, beta=7) which has mode=0.250, median=0.286, and
    mean=0.300.  Only the latter (which corresponds with R6) gives the
    desired cut point with 30% of the population falling below that
    value, making it comparable to a result from an inv_cdf() function.
    The R6 exclusive method is also idempotent.

    For describing population data where the end points are known to
    be included in the data, the R7 inclusive method is a reasonable
    choice.  Instead of the mean, it uses the mode of the beta
    distribution for the interior points.  Per Hyndman & Fan, "One nice
    property is that the vertices of Q7(p) divide the range into n - 1
    intervals, and exactly 100p% of the intervals lie to the left of
    Q7(p) and 100(1 - p)% of the intervals lie to the right of Q7(p)."

    If needed, other methods could be added.  However, for now, the
    position is that fewer options make for easier choices and that
    external packages can be used for anything more advanced.

### `statistics.scope(list)`

Syntax: `statistics.scope(list)`

Calculates the scope of a list of numbers: `max(list) - min(list)`.

### `statistics.mode(list)`

Syntax: `statistics.mode(list)`

Calculates the mode of a list of numbers, i.e. the most common value.

### `statistics.multimode(value)`

Syntax: `statistics.multimode(value)`

Calculates the modes of a list or a str, i.e. the most common values. It returns a list.
