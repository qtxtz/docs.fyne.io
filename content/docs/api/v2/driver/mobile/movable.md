---
tags: [api]
title: mobile.Movable
slug: movable

aliases:
- /api/driver/mobile/movable
- /api/driver/mobile/movable.html
- /api/v2.0/driver/mobile/movable
- /api/v2.0/driver/mobile/movable.html
- /api/v2.1/driver/mobile/movable
- /api/v2.1/driver/mobile/movable.html
- /api/v2.2/driver/mobile/movable
- /api/v2.2/driver/mobile/movable.html
- /api/v2.3/driver/mobile/movable
- /api/v2.3/driver/mobile/movable.html
- /api/v2.4/driver/mobile/movable
- /api/v2.4/driver/mobile/movable.html
- /api/v2.5/driver/mobile/movable
- /api/v2.5/driver/mobile/movable.html
- /api/v2.6/driver/mobile/movable
- /api/v2.6/driver/mobile/movable.html
- /api/v2.7/driver/mobile/movable
- /api/v2.7/driver/mobile/movable.html

package: fyne.io/fyne/v2/driver/mobile
---


---
```go
import "fyne.io/fyne/v2/driver/mobile"
```

## Usage

#### type Movable

```go
type Movable interface {
	TouchMoved(*TouchEvent)
}
```

Movable represents a mobile touch event dragging across the screen. Where multiple fingers are moving then will be reported as different events. The ID of the TouchEvent indicates which finger moved.


<div class="since">Since: <code>
2.8</code></div>
