# Debug

*[Source code](https://github.com/jd-develop/nougaro/blob/main/lib_/debug.noug)*

Debug is a lib that contains some debugging tools.

## Constants
* `debug.is_debug_enabled`: 1 if DEBUG mode is enabled, else 0
* `debug.should_print_context`: 1 if PRINT CONTEXT debug option is enabled, else 0
* `debug.should_print_time` (new in 0.20.0-beta): 1 if PRINT TIME debug option is enabled, else 0

## Functions
### `debug.debug_mode_enable`
Syntax: `debug.debug_mode_enable`

Enables DEBUG mode.

### `debug.enable`
Alias for `debug.debug_mode_enable`

### `debug.debug_mode_disable`
Syntax: `debug.debug_mode_disable`

Disables DEBUG mode.

### `debug.disable`
Alias for `debug.debug_mode_disable`

### `debug.print_context`
Syntax: `debug.print_context`

Enables PRINT CONTEXT debug option.

### `debug.stop_print_context`
Syntax: `debug.stop_print_context`

Disables PRINT CONTEXT debug option.

### `debug.print_time`
!!! note ""
    Added in 0.20.0-beta

Syntax: `debug.print_time`

Enables PRINT TIME debug option.

### `debug.stop_print_time`
!!! note ""
    Added in 0.20.0-beta
Syntax: `debug.stop_print_time`

Disables PRINT TIME debug option.

### `debug.enable_all`
!!! note "Changed in 0.20.0-beta"
    Now also enables PRINT TIME debug option.

Syntax: `debug.enable_all`

Enables DEBUG mode with all its options

### `debug.disable_all`
!!! note "Changed in 0.20.0-beta"
    Now also disables PRINT TIME debug option.

Syntax: `debug.disable_all`

Disables DEBUG mode and all its options.
