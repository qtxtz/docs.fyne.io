---
tags: [api]
title: canvas.Ellipse
slug: ellipse

aliases:
- /api/canvas/ellipse
- /api/canvas/ellipse.html
- /api/v2.0/canvas/ellipse
- /api/v2.0/canvas/ellipse.html
- /api/v2.1/canvas/ellipse
- /api/v2.1/canvas/ellipse.html
- /api/v2.2/canvas/ellipse
- /api/v2.2/canvas/ellipse.html
- /api/v2.3/canvas/ellipse
- /api/v2.3/canvas/ellipse.html
- /api/v2.4/canvas/ellipse
- /api/v2.4/canvas/ellipse.html
- /api/v2.5/canvas/ellipse
- /api/v2.5/canvas/ellipse.html
- /api/v2.6/canvas/ellipse
- /api/v2.6/canvas/ellipse.html
- /api/v2.7/canvas/ellipse
- /api/v2.7/canvas/ellipse.html

package: fyne.io/fyne/v2/canvas
---


---
```go
import "fyne.io/fyne/v2/canvas"
```

## Usage

#### type Ellipse

```go
type Ellipse struct {
	FillColor   color.Color // The ellipse fill color
	StrokeColor color.Color // The ellipse stroke color
	StrokeWidth float32     // The stroke width of the ellipse
	Shadow      Shadow      // Support shadow configuration
}
```

Ellipse describes a colored ellipse primitive in a Fyne canvas with radii being half the width and height of its size.


<div class="since">Since: <code>
2.8</code></div>

#### func  NewEllipse

```go
func NewEllipse(color color.Color) *Ellipse
```
NewEllipse returns a new Ellipse instance

#### func (*Ellipse) Hide

```go
func (e *Ellipse) Hide()
```
Hide will set this ellipse to not be visible

#### func (*Ellipse) MinSize

```go
func (o *Ellipse) MinSize() fyne.Size
```
MinSize returns the specified minimum size, if set, or {1, 1} otherwise.

#### func (*Ellipse) Move

```go
func (e *Ellipse) Move(pos fyne.Position)
```
Move the ellipse to a new position, relative to its parent / canvas

#### func (*Ellipse) Position

```go
func (o *Ellipse) Position() fyne.Position
```
Position gets the current position of this canvas object, relative to its parent.

#### func (*Ellipse) Refresh

```go
func (e *Ellipse) Refresh()
```
Refresh causes this ellipse to be redrawn with its configured state.

#### func (*Ellipse) Resize

```go
func (e *Ellipse) Resize(s fyne.Size)
```
Resize on a ellipse updates the new size of this object. If it has a stroke width this will cause it to Refresh.

#### func (*Ellipse) SetMinSize

```go
func (o *Ellipse) SetMinSize(size fyne.Size)
```
SetMinSize specifies the smallest size this object should be.

#### func (*Ellipse) Show

```go
func (o *Ellipse) Show()
```
Show will set this object to be visible.

#### func (*Ellipse) Size

```go
func (o *Ellipse) Size() fyne.Size
```
Size returns the current size of this canvas object.

#### func (*Ellipse) Visible

```go
func (o *Ellipse) Visible() bool
```
Visible returns true if this object is visible, false otherwise.
