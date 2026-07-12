---
title: Clip

weight: 4110

aliases:
- /container/clip.html
---

The Clip container shows only the part of its content that falls
inside its own bounds - anything that would overflow is simply not
drawn. Create one with `container.NewClip(...)` passing the
[fyne.CanvasObject](/api/v2/fyne/canvasobject/#type--canvasobject) that should be clipped.

This is useful when an element is deliberately larger than the space
you want it to occupy, for example an image that should fill a header
area without distorting, or an animation that moves through a fixed
window. A clip does not add scrollbars and the user cannot move the
content within it - if that is what you need then use the
[Scroll](/container/scroll) container, which clips as part of its job.

The minimum size of a clip is tiny, because there is no requirement
for the content to fit. The size of the clip therefore comes from the
layout it is placed in, and the content is positioned at the top left
and drawn at its own size.

Added in Fyne 2.7.

```go
package main

import (
	"image/color"

	"fyne.io/fyne/v2"
	"fyne.io/fyne/v2/app"
	"fyne.io/fyne/v2/canvas"
	"fyne.io/fyne/v2/container"
)

func main() {
	myApp := app.New()
	myWindow := myApp.NewWindow("Clip Container")

	big := canvas.NewRectangle(color.NRGBA{R: 0x33, G: 0x99, B: 0xcc, A: 0xff})
	big.SetMinSize(fyne.NewSize(400, 400)) // much bigger than the window

	clip := container.NewClip(big)

	myWindow.SetContent(clip)
	myWindow.Resize(fyne.NewSize(150, 150)) // only this much will be drawn
	myWindow.ShowAndRun()
}
```
