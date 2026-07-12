---
tags: [api]
title: canvas.ArbitraryPolygon
slug: arbitrarypolygon

aliases:
- /api/canvas/arbitrarypolygon
- /api/canvas/arbitrarypolygon.html
- /api/v2.0/canvas/arbitrarypolygon
- /api/v2.0/canvas/arbitrarypolygon.html
- /api/v2.1/canvas/arbitrarypolygon
- /api/v2.1/canvas/arbitrarypolygon.html
- /api/v2.2/canvas/arbitrarypolygon
- /api/v2.2/canvas/arbitrarypolygon.html
- /api/v2.3/canvas/arbitrarypolygon
- /api/v2.3/canvas/arbitrarypolygon.html
- /api/v2.4/canvas/arbitrarypolygon
- /api/v2.4/canvas/arbitrarypolygon.html
- /api/v2.5/canvas/arbitrarypolygon
- /api/v2.5/canvas/arbitrarypolygon.html
- /api/v2.6/canvas/arbitrarypolygon
- /api/v2.6/canvas/arbitrarypolygon.html
- /api/v2.7/canvas/arbitrarypolygon
- /api/v2.7/canvas/arbitrarypolygon.html

package: fyne.io/fyne/v2/canvas
---


---
```go
import "fyne.io/fyne/v2/canvas"
```

## Usage

#### type ArbitraryPolygon

```go
type ArbitraryPolygon struct {
	Points           []fyne.Position // Vertices in coordinates relative to the object. If NormalizedPoints is true, these are (0.0 to 1.0), otherwise absolute
	NormalizedPoints bool            // True if Points are specified in normalized coordinates (0.0 to 1.0) relative to the object's size
	CornerRadii      []float32       // Per-corner rounding radius, must match len(Points), missing entries default to 0
	FillColor        color.Color     // The polygon fill color
	StrokeColor      color.Color     // The polygon stroke color
	StrokeWidth      float32         // The stroke width of the polygon
}
```

ArbitraryPolygon describes a colored arbitrary polygon primitive in a Fyne canvas. The polygon is defined by a list of vertex positions in clockwise order, relative to the object (top-left is (0,0), bottom-right is (width,height)). Each corner can have an individually specified rounding radius. The implementation is limited to 16 vertices.


<div class="since">Since: <code>
2.8</code></div>

#### func  NewArbitraryPolygon

```go
func NewArbitraryPolygon(points []fyne.Position, fill color.Color) *ArbitraryPolygon
```
NewArbitraryPolygon returns a new ArbitraryPolygon instance

#### func (*ArbitraryPolygon) Hide

```go
func (p *ArbitraryPolygon) Hide()
```
Hide will set this arbitrary polygon to not be visible

#### func (*ArbitraryPolygon) MinSize

```go
func (o *ArbitraryPolygon) MinSize() fyne.Size
```
MinSize returns the specified minimum size, if set, or {1, 1} otherwise.

#### func (*ArbitraryPolygon) Move

```go
func (p *ArbitraryPolygon) Move(pos fyne.Position)
```
Move the arbitrary polygon to a new position, relative to its parent / canvas

#### func (*ArbitraryPolygon) Position

```go
func (o *ArbitraryPolygon) Position() fyne.Position
```
Position gets the current position of this canvas object, relative to its parent.

#### func (*ArbitraryPolygon) Refresh

```go
func (p *ArbitraryPolygon) Refresh()
```
Refresh causes this arbitrary polygon to be redrawn with its configured state.

#### func (*ArbitraryPolygon) Resize

```go
func (p *ArbitraryPolygon) Resize(s fyne.Size)
```
Resize on an arbitrary polygon updates the new size of this object.

#### func (*ArbitraryPolygon) SetMinSize

```go
func (o *ArbitraryPolygon) SetMinSize(size fyne.Size)
```
SetMinSize specifies the smallest size this object should be.

#### func (*ArbitraryPolygon) Show

```go
func (o *ArbitraryPolygon) Show()
```
Show will set this object to be visible.

#### func (*ArbitraryPolygon) Size

```go
func (o *ArbitraryPolygon) Size() fyne.Size
```
Size returns the current size of this canvas object.

#### func (*ArbitraryPolygon) Visible

```go
func (o *ArbitraryPolygon) Visible() bool
```
Visible returns true if this object is visible, false otherwise.
