---
tags: [api]
title: mobile.TouchEvent
slug: touchevent

aliases:
- /api/driver/mobile/touchevent
- /api/driver/mobile/touchevent.html
- /api/v2.0/driver/mobile/touchevent
- /api/v2.0/driver/mobile/touchevent.html
- /api/v2.1/driver/mobile/touchevent
- /api/v2.1/driver/mobile/touchevent.html
- /api/v2.2/driver/mobile/touchevent
- /api/v2.2/driver/mobile/touchevent.html
- /api/v2.3/driver/mobile/touchevent
- /api/v2.3/driver/mobile/touchevent.html
- /api/v2.4/driver/mobile/touchevent
- /api/v2.4/driver/mobile/touchevent.html
- /api/v2.5/driver/mobile/touchevent
- /api/v2.5/driver/mobile/touchevent.html
- /api/v2.6/driver/mobile/touchevent
- /api/v2.6/driver/mobile/touchevent.html
- /api/v2.7/driver/mobile/touchevent
- /api/v2.7/driver/mobile/touchevent.html

package: fyne.io/fyne/v2/driver/mobile
---


---
```go
import "fyne.io/fyne/v2/driver/mobile"
```

## Usage

#### type TouchEvent

```go
type TouchEvent struct {
	fyne.PointEvent

	// ID represents the current ID of this touch, used to differentiate multiple fingers during a gesture.
	// The ID value may be re-used after that touch is released from the device (via TouchUp or TouchCancel).
	//
	// Since: 2.8
	ID int
}
```

TouchEvent contains data relating to mobile touch events
