# Noug Version

*[Source code](https://github.com/jd-develop/nougaro/blob/main/lib_/noug_version.noug)*

The `noug_version` module can be imported with the statement `import noug_version`.

The `noug_version` module is used to have better informations about the current Nougaro version.

!!! note
    Nougaro uses [semantic versionning](https://semver.org). We recommend you to read the whole semver specification.

## Constants
Examples are given considering the version `3.14.15-rc.92`

* `noug_version.major`: integer of the MAJOR version (`3`)
* `noug_version.minor`: integer of the MINOR version (`14`)
* `noug_version.patch`: integer of the PATCH version (`15`)
* `noug_version.phase`: string of the PHASE name (`"rc"`). Usually `alpha`, `beta`, `rc`, `stable`.
* `noug_version.release_serial`: integer of the MINOR INDEV version (`92`). It resets when the phase switches back to `stable`. When the version is under the form `3.14.15-stable` or `0.16.0-beta`, this number is `0`.
* `noug_version.version_list`: list under the form `[major, minor, patch, phase, release_serial]` (in our example: `[3, 14, 15, "rc", 92]`)

!!! note "Changed in 0.19.0 and 0.20.0"
    `noug_version.release_serial` is the new name for `noug_version.phase_minor` in 0.19.0-beta. `noug_version.phase_minor` has been removed in 0.20.0-beta.

## Functions
### `noug_version.clean_version_for_gh`

!!! note ""
    Added in 0.19.0-beta

Syntax: `noug_version.clean_version_for_gh()`

Generates a beautiful str for the GitHub issues or PRs.
