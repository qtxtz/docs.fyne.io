---
tags: [api]
title: canvas.Polygon
slug: polygon

aliases:
- /api/canvas/polygon
- /api/canvas/polygon.html
- /api/v2.0/canvas/polygon
- /api/v2.0/canvas/polygon.html
- /api/v2.1/canvas/polygon
- /api/v2.1/canvas/polygon.html
- /api/v2.2/canvas/polygon
- /api/v2.2/canvas/polygon.html
- /api/v2.3/canvas/polygon
- /api/v2.3/canvas/polygon.html
- /api/v2.4/canvas/polygon
- /api/v2.4/canvas/polygon.html
- /api/v2.5/canvas/polygon
- /api/v2.5/canvas/polygon.html
- /api/v2.6/canvas/polygon
- /api/v2.6/canvas/polygon.html
- /api/v2.7/canvas/polygon
- /api/v2.7/canvas/polygon.html

package: fyne.io/fyne/v2/canvas
---


---
```go
import "fyne.io/fyne/v2/canvas"
```

## Usage

#### type Polygon

```go
type Polygon = RegularPolygon
```

Polygon describes a colored regular polygon primitive in a Fyne canvas. The rendered portion will be in the center of the available space.

<div class="deprecated"> Deprecated: Use [RegularPolygon] instead</div>


<div class="since">Since: <code>
2.7</code></div>

#### func  NewPolygon

```go
func NewPolygon(sides uint, color color.Color) *Polygon
```
NewPolygon returns a new Polygon instance

<div class="deprecated"> Deprecated: Use [NewRegularPolygon] instead</div>


<div class="since">Since: <code>
2.7</code></div>
