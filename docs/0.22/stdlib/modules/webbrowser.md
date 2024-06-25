# Webbrowser
!!! note ""
    Added in 0.19.0-beta

The `webbrowser` module can be imported with the statement `import webbrowser`.

Convenient web-browser controller. The webbrowser module allows you to open pages in the browser.

## Functions
### `webbrowser.open`

Syntax: `webbrowser.open(url, <new=0>, <autoraise=True>)`

Displays `url` using the default browser.
If `new` is 0, the `url` is opened in the same browser window if possible.
If `new` is 1, a new browser window is opened if possible.
If `new` is 2, a new tab is opened if possible.
If `autoraise` is True, the window is raised if possible (note that under many window managers this will occur
regardless of the setting of this variable).
