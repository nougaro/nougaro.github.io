# Time

The `time` module can be imported with the statement `import time`.

The `time` module is used to sleep for seconds or milliseconds, and to know current time, timezone and system’s epoch.

## Constants
* `time.timezone`: the timezone (number of seconds to add to GMT)

## Functions
### `time.sleep`

Syntax: `time.sleep(seconds)`

Pauses the program for seconds ([int or float](../../Language/06values.md#numbers)) and do nothing. Returns [`None`](../../Language/06values.md#numbers).

### `time.sleep_milliseconds`

Syntax: `time.sleep_milliseconds(milliseconds)`

Pauses the program for milliseconds ([integer](../../Language/06values.md#numbers)) and do nothing. Returns `None`.

### `time.time`

Syntax: `time.time()`

Returns the float value of the time in seconds since the Epoch (system-dependent, check your epoch with [`time.epoch()`](#timeepoch)).

### `time.epoch`

Syntax: `time.epoch()`

Returns the str value of the Epoch of your system.
