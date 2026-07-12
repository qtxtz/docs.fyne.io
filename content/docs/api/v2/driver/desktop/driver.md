---
tags: [api]
title: desktop.Driver
slug: driver

aliases:
- /api/driver/desktop/driver
- /api/driver/desktop/driver.html
- /api/v2.0/driver/desktop/driver
- /api/v2.0/driver/desktop/driver.html
- /api/v2.1/driver/desktop/driver
- /api/v2.1/driver/desktop/driver.html
- /api/v2.2/driver/desktop/driver
- /api/v2.2/driver/desktop/driver.html
- /api/v2.3/driver/desktop/driver
- /api/v2.3/driver/desktop/driver.html
- /api/v2.4/driver/desktop/driver
- /api/v2.4/driver/desktop/driver.html
- /api/v2.5/driver/desktop/driver
- /api/v2.5/driver/desktop/driver.html
- /api/v2.6/driver/desktop/driver
- /api/v2.6/driver/desktop/driver.html
- /api/v2.7/driver/desktop/driver
- /api/v2.7/driver/desktop/driver.html

package: fyne.io/fyne/v2/driver/desktop
---


---
```go
import "fyne.io/fyne/v2/driver/desktop"
```

## Usage

#### type Driver

```go
type Driver interface {
	// CreateSplashWindow creates a new borderless window that is centered on screen
	CreateSplashWindow() fyne.Window

	// CurrentKeyModifiers returns the set of key modifiers that are currently active
	//
	// Since: 2.4
	CurrentKeyModifiers() fyne.KeyModifier

	// HasSecondaryDisplay returns true if there are more than one screens available on this computer.
	// This is commonly used alongside the desktop Window.RequestFullScreenSecondary call.
	//
	// Since: 2.8
	HasSecondaryDisplay() bool
}
```

Driver represents the extended capabilities of a desktop driver
