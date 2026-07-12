---
title: Split

weight: 4090

aliases:
- /container/split.html
- /tour/container/split
---

The Split container divides the space it is given between two
children, with a draggable divider between them so the user can
decide how much room each one gets. It is the basis of the familiar
sidebar-and-content arrangement.

Use `container.NewHSplit(...)` for a side by side arrangement, where
the parameters are the leading (left) and trailing (right) content.
`container.NewVSplit(...)` stacks the two children instead, taking
the top and the bottom content.

The `Offset` field is the proportion of the space given to the first
child, from `0.0` to `1.0`, and it defaults to `0.5` for an even
split. Call `SetOffset(...)` to move the divider from your code - for
example to restore the position the user last chose.

Because a split container gives its children whatever space is
available, rather than their minimum size, it is a good idea to wrap
content that may not fit in a [Scroll](/container/scroll) container.

```go
package main

import (
	"fyne.io/fyne/v2"
	"fyne.io/fyne/v2/app"
	"fyne.io/fyne/v2/container"
	"fyne.io/fyne/v2/widget"
)

func main() {
	myApp := app.New()
	myWindow := myApp.NewWindow("Split Container")

	left := widget.NewLabel("Left side")
	right := widget.NewLabel("Right side")

	split := container.NewHSplit(left, right)
	split.SetOffset(0.3) // the left side gets 30% of the space

	myWindow.SetContent(split)
	myWindow.Resize(fyne.NewSize(400, 200))
	myWindow.ShowAndRun()
}
```
