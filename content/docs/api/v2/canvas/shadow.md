---
tags: [api]
title: canvas.Shadow
slug: shadow

aliases:
- /api/canvas/shadow
- /api/canvas/shadow.html
- /api/v2.0/canvas/shadow
- /api/v2.0/canvas/shadow.html
- /api/v2.1/canvas/shadow
- /api/v2.1/canvas/shadow.html
- /api/v2.2/canvas/shadow
- /api/v2.2/canvas/shadow.html
- /api/v2.3/canvas/shadow
- /api/v2.3/canvas/shadow.html
- /api/v2.4/canvas/shadow
- /api/v2.4/canvas/shadow.html
- /api/v2.5/canvas/shadow
- /api/v2.5/canvas/shadow.html
- /api/v2.6/canvas/shadow
- /api/v2.6/canvas/shadow.html
- /api/v2.7/canvas/shadow
- /api/v2.7/canvas/shadow.html

package: fyne.io/fyne/v2/canvas
---


---
```go
import "fyne.io/fyne/v2/canvas"
```

## Usage

#### type Shadow

```go
type Shadow struct {
	Color      color.Color   // Color of the shadow.
	BlurRadius float32       // A value of 0 produces no blur, while larger values produce bigger and lighter shadow.
	Spread     float32       // Spread of the shadow (how far out to draw before fading - negative values make it smaller).
	Offset     fyne.Position // Offset of the shadow relative to the content. Positive values move the shadow to the right (x) and down (y) of the element.
	Variant    ShadowVariant // Variation of shadow (DropShadow or BoxShadow).
}
```

Shadow provides base functionality for objects that can have a Shadow. Intended to be embedded in other structs to add Shadow support.


<div class="since">Since: <code>
2.8</code></div>
