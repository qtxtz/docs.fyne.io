---
tags: [api]
title: canvas.BezierCurve
slug: beziercurve

aliases:
- /api/canvas/beziercurve
- /api/canvas/beziercurve.html
- /api/v2.0/canvas/beziercurve
- /api/v2.0/canvas/beziercurve.html
- /api/v2.1/canvas/beziercurve
- /api/v2.1/canvas/beziercurve.html
- /api/v2.2/canvas/beziercurve
- /api/v2.2/canvas/beziercurve.html
- /api/v2.3/canvas/beziercurve
- /api/v2.3/canvas/beziercurve.html
- /api/v2.4/canvas/beziercurve
- /api/v2.4/canvas/beziercurve.html
- /api/v2.5/canvas/beziercurve
- /api/v2.5/canvas/beziercurve.html
- /api/v2.6/canvas/beziercurve
- /api/v2.6/canvas/beziercurve.html
- /api/v2.7/canvas/beziercurve
- /api/v2.7/canvas/beziercurve.html

package: fyne.io/fyne/v2/canvas
---


---
```go
import "fyne.io/fyne/v2/canvas"
```

## Usage

#### type BezierCurve

```go
type BezierCurve struct {
	StartPoint    fyne.Position   // Starting point of the bezier curve
	EndPoint      fyne.Position   // Ending point of the bezier curve
	ControlPoints []fyne.Position // Max 2 control points (0 for linear, 1 for quadratic, 2 for cubic)
	StrokeColor   color.Color     // The bezier curve stroke color
	StrokeWidth   float32         // The stroke width of the bezier curve
}
```

BezierCurve describes a colored bezier curve primitive in a Fyne canvas. It supports linear (0 control point), quadratic (1 control point) and cubic (2 control points) bezier curves. The curve is drawn within the object's position and size, with the start, end, and control points specified relative to the object. Top-left position is (0,0) and bottom-right is (height,width). Increasing the X coordinate moves to the right, increasing the Y coordinate moves downwards. Negative coordinates are not supported.


<div class="since">Since: <code>
2.8</code></div>

#### func  NewCubicBezierCurve

```go
func NewCubicBezierCurve(startPoint, controlPoint1, controlPoint2, endPoint fyne.Position, color color.Color) *BezierCurve
```
NewCubicBezierCurve creates a cubic bezier curve with 2 control points

#### func  NewLinearBezierCurve

```go
func NewLinearBezierCurve(startPoint, endPoint fyne.Position, color color.Color) *BezierCurve
```
NewLinearBezierCurve creates a linear bezier curve with 0 control points

#### func  NewQuadraticBezierCurve

```go
func NewQuadraticBezierCurve(startPoint, controlPoint, endPoint fyne.Position, color color.Color) *BezierCurve
```
NewQuadraticBezierCurve creates a quadratic bezier curve with 1 control points

#### func (*BezierCurve) Hide

```go
func (r *BezierCurve) Hide()
```
Hide will set this bezier curve to not be visible

#### func (*BezierCurve) MinSize

```go
func (o *BezierCurve) MinSize() fyne.Size
```
MinSize returns the specified minimum size, if set, or {1, 1} otherwise.

#### func (*BezierCurve) Move

```go
func (r *BezierCurve) Move(pos fyne.Position)
```
Move the bezier curve to a new position, relative to its parent / canvas

#### func (*BezierCurve) Position

```go
func (o *BezierCurve) Position() fyne.Position
```
Position gets the current position of this canvas object, relative to its parent.

#### func (*BezierCurve) Refresh

```go
func (r *BezierCurve) Refresh()
```
Refresh causes this bezier curve to be redrawn with its configured state.

#### func (*BezierCurve) Resize

```go
func (r *BezierCurve) Resize(s fyne.Size)
```
Resize on a bezier curve updates the new size of this object. If it has a stroke width this will cause it to Refresh.

#### func (*BezierCurve) SetMinSize

```go
func (o *BezierCurve) SetMinSize(size fyne.Size)
```
SetMinSize specifies the smallest size this object should be.

#### func (*BezierCurve) Show

```go
func (o *BezierCurve) Show()
```
Show will set this object to be visible.

#### func (*BezierCurve) Size

```go
func (o *BezierCurve) Size() fyne.Size
```
Size returns the current size of this canvas object.

#### func (*BezierCurve) Visible

```go
func (o *BezierCurve) Visible() bool
```
Visible returns true if this object is visible, false otherwise.
