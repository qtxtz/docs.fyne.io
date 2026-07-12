---
tags: [api]
title: software.WindowlessCanvas
slug: windowlesscanvas

aliases:
- /api/driver/software/windowlesscanvas
- /api/driver/software/windowlesscanvas.html
- /api/v2.0/driver/software/windowlesscanvas
- /api/v2.0/driver/software/windowlesscanvas.html
- /api/v2.1/driver/software/windowlesscanvas
- /api/v2.1/driver/software/windowlesscanvas.html
- /api/v2.2/driver/software/windowlesscanvas
- /api/v2.2/driver/software/windowlesscanvas.html
- /api/v2.3/driver/software/windowlesscanvas
- /api/v2.3/driver/software/windowlesscanvas.html
- /api/v2.4/driver/software/windowlesscanvas
- /api/v2.4/driver/software/windowlesscanvas.html
- /api/v2.5/driver/software/windowlesscanvas
- /api/v2.5/driver/software/windowlesscanvas.html
- /api/v2.6/driver/software/windowlesscanvas
- /api/v2.6/driver/software/windowlesscanvas.html
- /api/v2.7/driver/software/windowlesscanvas
- /api/v2.7/driver/software/windowlesscanvas.html

package: fyne.io/fyne/v2/driver/software
---


---
```go
import "fyne.io/fyne/v2/driver/software"
```

## Usage

#### type WindowlessCanvas

```go
type WindowlessCanvas interface {
	fyne.Canvas

	Padded() bool
	Resize(fyne.Size)
	SetPadded(bool)
	SetScale(float32)
}
```

WindowlessCanvas provides functionality for a canvas to operate without a window


<div class="since">Since: <code>
2.9</code></div>

#### func  NewCanvas

```go
func NewCanvas() WindowlessCanvas
```
NewCanvas creates a new canvas in memory that can render without hardware support.

#### func  NewCanvasWithPainter

```go
func NewCanvasWithPainter(painter driver.Painter) WindowlessCanvas
```
NewCanvasWithPainter creates a new canvas in memory that can render without hardware support which uses the given driver.Painter for #Capture().


<div class="since">Since: <code>
2.8</code></div>

#### func  NewTransparentCanvas

```go
func NewTransparentCanvas() WindowlessCanvas
```
NewTransparentCanvas creates a new canvas in memory that can render without hardware support without a background color.


<div class="since">Since: <code>
2.2</code></div>

#### func  NewTransparentCanvasWithPainter

```go
func NewTransparentCanvasWithPainter(painter driver.Painter) WindowlessCanvas
```
NewTransparentCanvasWithPainter creates a new canvas in memory that can render without hardware support which uses the given driver.Painter for #Capture() without a background color.


<div class="since">Since: <code>
2.8</code></div>
