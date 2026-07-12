---
tags: [api]
title: desktop.Window
slug: window

aliases:
- /api/driver/desktop/window
- /api/driver/desktop/window.html
- /api/v2.0/driver/desktop/window
- /api/v2.0/driver/desktop/window.html
- /api/v2.1/driver/desktop/window
- /api/v2.1/driver/desktop/window.html
- /api/v2.2/driver/desktop/window
- /api/v2.2/driver/desktop/window.html
- /api/v2.3/driver/desktop/window
- /api/v2.3/driver/desktop/window.html
- /api/v2.4/driver/desktop/window
- /api/v2.4/driver/desktop/window.html
- /api/v2.5/driver/desktop/window
- /api/v2.5/driver/desktop/window.html
- /api/v2.6/driver/desktop/window
- /api/v2.6/driver/desktop/window.html
- /api/v2.7/driver/desktop/window
- /api/v2.7/driver/desktop/window.html

package: fyne.io/fyne/v2/driver/desktop
---


---
```go
import "fyne.io/fyne/v2/driver/desktop"
```

## Usage

#### type Window

```go
type Window interface {
	// RequestFullScreenSecondary asks for a window to fullscreen on a non-primary monitor.
	// When there is only one screen it will fullscreen on the primary monitor.
	RequestFullScreenSecondary()

	// RequestAlwaysOnTop asks for the window to remain above other windows, call before [Show].
	// This is subject to support on the current system and with the caveat that the window manager
	// may decide that other windows or panels remain above this one.
	RequestAlwaysOnTop()

	// RequestPosition asks the operating to position this window at the x, y coordinate
	// of the native system. These values may be scaled and so not necessarily pixel values.
	// This request may be ignored (for example Linux Wayland).
	// There is no contract of what these values represent and on multiple monitors may be greater
	// than the coordinates of the current monitor.
	RequestPosition(x, y int)
}
```

Window describes desktop specific window features


<div class="since">Since: <code>
2.8</code></div>
