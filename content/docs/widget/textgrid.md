---
title: TextGrid

weight: 5110

aliases:
- /widget/textgrid.html
- /tour/widget/textgrid
---

The text grid widget is a monospaced grid of characters where each
cell can have its own style. It is designed as the basis of a text
editor, code preview or terminal emulator, so it does not scroll or
handle input itself - place it inside a scroll container and set the
content as your application requires.

An empty grid is created with [widget.NewTextGrid()](/api/v2/widget/textgrid/#func--newtextgrid), or you can
load some content directly using [widget.NewTextGridFromString()](/api/v2/widget/textgrid/#func--newtextgridfromstring).
Calling `SetText(...)` will replace all of the content, whilst
`SetRow(...)` and `SetCell(...)` allow individual rows and cells to
be updated without touching the rest of the grid.

Styling is applied per cell using a [widget.TextGridStyle](/api/v2/widget/textgridstyle/#type--textgridstyle) - the
[widget.CustomTextGridStyle](/api/v2/widget/customtextgridstyle/#type--customtextgridstyle) type lets you specify foreground and
background colours. The `SetStyleRange(...)` helper applies a style
to every cell between two positions, which is handy for syntax
highlighting or a selection.

The `ShowLineNumbers` and `ShowWhitespace` fields add a line number
column and visible whitespace characters respectively.

```go
package main

import (
	"image/color"

	"fyne.io/fyne/v2/app"
	"fyne.io/fyne/v2/widget"
)

func main() {
	myApp := app.New()
	myWindow := myApp.NewWindow("TextGrid Widget")

	grid := widget.NewTextGridFromString("Hello there\nThis is a text grid")
	grid.ShowLineNumbers = true

	highlight := &widget.CustomTextGridStyle{FGColor: color.NRGBA{R: 0xcc, A: 0xff}}
	grid.SetStyleRange(0, 0, 0, 4, highlight)

	myWindow.SetContent(grid)
	myWindow.ShowAndRun()
}
```
