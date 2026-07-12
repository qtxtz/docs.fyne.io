---
tags: [api]
title: canvas.ShadowVariant
slug: shadowvariant

aliases:
- /api/canvas/shadowvariant
- /api/canvas/shadowvariant.html
- /api/v2.0/canvas/shadowvariant
- /api/v2.0/canvas/shadowvariant.html
- /api/v2.1/canvas/shadowvariant
- /api/v2.1/canvas/shadowvariant.html
- /api/v2.2/canvas/shadowvariant
- /api/v2.2/canvas/shadowvariant.html
- /api/v2.3/canvas/shadowvariant
- /api/v2.3/canvas/shadowvariant.html
- /api/v2.4/canvas/shadowvariant
- /api/v2.4/canvas/shadowvariant.html
- /api/v2.5/canvas/shadowvariant
- /api/v2.5/canvas/shadowvariant.html
- /api/v2.6/canvas/shadowvariant
- /api/v2.6/canvas/shadowvariant.html
- /api/v2.7/canvas/shadowvariant
- /api/v2.7/canvas/shadowvariant.html

package: fyne.io/fyne/v2/canvas
---


---
```go
import "fyne.io/fyne/v2/canvas"
```

## Usage

#### type ShadowVariant

```go
type ShadowVariant int
```

ShadowVariant indicates a variation of a shadow.


<div class="since">Since: <code>
2.8</code></div>

```go
const (
	// DropShadow represents a shadow effect that is rendered exclusively outside the boundaries of the object,
	// following the object's shape and not appearing beneath its filled area.
	//
	// Since: 2.8
	DropShadow ShadowVariant = iota
	// BoxShadow represents a shadow effect that is rendered both behind and outside the object,
	// appearing as a blurred rectangle that extends beneath the object's filled area as well as beyond its edges.
	//
	// Since: 2.8
	BoxShadow
)
```
