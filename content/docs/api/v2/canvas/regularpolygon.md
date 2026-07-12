---
tags: [api]
title: canvas.RegularPolygon
slug: regularpolygon

aliases:
- /api/canvas/regularpolygon
- /api/canvas/regularpolygon.html
- /api/v2.0/canvas/regularpolygon
- /api/v2.0/canvas/regularpolygon.html
- /api/v2.1/canvas/regularpolygon
- /api/v2.1/canvas/regularpolygon.html
- /api/v2.2/canvas/regularpolygon
- /api/v2.2/canvas/regularpolygon.html
- /api/v2.3/canvas/regularpolygon
- /api/v2.3/canvas/regularpolygon.html
- /api/v2.4/canvas/regularpolygon
- /api/v2.4/canvas/regularpolygon.html
- /api/v2.5/canvas/regularpolygon
- /api/v2.5/canvas/regularpolygon.html
- /api/v2.6/canvas/regularpolygon
- /api/v2.6/canvas/regularpolygon.html
- /api/v2.7/canvas/regularpolygon
- /api/v2.7/canvas/regularpolygon.html

package: fyne.io/fyne/v2/canvas
---


---
```go
import "fyne.io/fyne/v2/canvas"
```

## Usage

#### type RegularPolygon

```go
type RegularPolygon struct {
	FillColor    color.Color // The polygon fill color
	StrokeColor  color.Color // The polygon stroke color
	StrokeWidth  float32     // The stroke width of the polygon
	CornerRadius float32     // The radius of the polygon corners
	Angle        float32     // Angle of polygon, in degrees (positive means clockwise, negative means counter-clockwise direction).
	Sides        uint        //	Amount of sides of polygon.
}
```

RegularPolygon describes a colored regular polygon primitive in a Fyne canvas. The rendered portion will be in the center of the available space.


<div class="since">Since: <code>
2.8</code></div>

#### func  NewRegularPolygon

```go
func NewRegularPolygon(sides uint, color color.Color) *RegularPolygon
```
NewRegularPolygon returns a new RegularPolygon instance


<div class="since">Since: <code>
2.8</code></div>

#### func (*RegularPolygon) Hide

```go
func (r *RegularPolygon) Hide()
```
Hide will set this polygon to not be visible

#### func (*RegularPolygon) MinSize

```go
func (o *RegularPolygon) MinSize() fyne.Size
```
MinSize returns the specified minimum size, if set, or {1, 1} otherwise.

#### func (*RegularPolygon) Move

```go
func (r *RegularPolygon) Move(pos fyne.Position)
```
Move the polygon to a new position, relative to its parent / canvas

#### func (*RegularPolygon) Position

```go
func (o *RegularPolygon) Position() fyne.Position
```
Position gets the current position of this canvas object, relative to its parent.

#### func (*RegularPolygon) Refresh

```go
func (r *RegularPolygon) Refresh()
```
Refresh causes this polygon to be redrawn with its configured state.

#### func (*RegularPolygon) Resize

```go
func (r *RegularPolygon) Resize(s fyne.Size)
```
Resize on a polygon updates the new size of this object. If it has a stroke width this will cause it to Refresh.

#### func (*RegularPolygon) SetMinSize

```go
func (o *RegularPolygon) SetMinSize(size fyne.Size)
```
SetMinSize specifies the smallest size this object should be.

#### func (*RegularPolygon) Show

```go
func (o *RegularPolygon) Show()
```
Show will set this object to be visible.

#### func (*RegularPolygon) Size

```go
func (o *RegularPolygon) Size() fyne.Size
```
Size returns the current size of this canvas object.

#### func (*RegularPolygon) Visible

```go
func (o *RegularPolygon) Visible() bool
```
Visible returns true if this object is visible, false otherwise.
