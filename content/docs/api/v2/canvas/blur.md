---
tags: [api]
title: canvas.Blur
slug: blur

aliases:
- /api/canvas/blur
- /api/canvas/blur.html
- /api/v2.0/canvas/blur
- /api/v2.0/canvas/blur.html
- /api/v2.1/canvas/blur
- /api/v2.1/canvas/blur.html
- /api/v2.2/canvas/blur
- /api/v2.2/canvas/blur.html
- /api/v2.3/canvas/blur
- /api/v2.3/canvas/blur.html
- /api/v2.4/canvas/blur
- /api/v2.4/canvas/blur.html
- /api/v2.5/canvas/blur
- /api/v2.5/canvas/blur.html
- /api/v2.6/canvas/blur
- /api/v2.6/canvas/blur.html
- /api/v2.7/canvas/blur
- /api/v2.7/canvas/blur.html

package: fyne.io/fyne/v2/canvas
---


---
```go
import "fyne.io/fyne/v2/canvas"
```

## Usage

#### type Blur

```go
type Blur struct {

	// Radius refers to how far from a point should be used to calculate the blur.
	// It must be greater than 0 but no more than 50.
	Radius float32

	// Radius used to round the corners of the blur region.
	CornerRadius float32
}
```

Blur creates a rectangular blur region on the output. All objects drawn under this will be blurred, any above will not be affected.


<div class="since">Since: <code>
2.8</code></div>

#### func  NewBlur

```go
func NewBlur(radius float32) *Blur
```
NewBlur returns a new Blur instance

#### func (*Blur) Hide

```go
func (b *Blur) Hide()
```
Hide will set this blur to not be visible

#### func (*Blur) MinSize

```go
func (o *Blur) MinSize() fyne.Size
```
MinSize returns the specified minimum size, if set, or {1, 1} otherwise.

#### func (*Blur) Move

```go
func (b *Blur) Move(pos fyne.Position)
```
Move the blur to a new position, relative to its parent / canvas

#### func (*Blur) Position

```go
func (o *Blur) Position() fyne.Position
```
Position gets the current position of this canvas object, relative to its parent.

#### func (*Blur) Refresh

```go
func (b *Blur) Refresh()
```
Refresh causes this blur to be redrawn with its configured state.

#### func (*Blur) Resize

```go
func (b *Blur) Resize(s fyne.Size)
```
Resize on a blur updates the new size of this object.

#### func (*Blur) SetMinSize

```go
func (o *Blur) SetMinSize(size fyne.Size)
```
SetMinSize specifies the smallest size this object should be.

#### func (*Blur) Show

```go
func (o *Blur) Show()
```
Show will set this object to be visible.

#### func (*Blur) Size

```go
func (o *Blur) Size() fyne.Size
```
Size returns the current size of this canvas object.

#### func (*Blur) Visible

```go
func (o *Blur) Visible() bool
```
Visible returns true if this object is visible, false otherwise.
