---
title: Scroll

weight: 4100

aliases:
- /container/scroll.html
- /tour/container/scroll
---

The Scroll container shows a portion of content that is larger than
the space available, adding scrollbars so the user can move around
it. Wrap any [fyne.CanvasObject](/api/v2/fyne/canvasobject/#type--canvasobject) using `container.NewScroll(...)`
and it will be given its minimum size, with anything that does not
fit being scrolled to.

If you only want movement in one direction then use
`container.NewVScroll(...)` or `container.NewHScroll(...)`, which
scroll vertically and horizontally respectively. A vertical scroll is
the usual choice for a long form or document, as the content can then
grow downwards whilst still fitting the width of the window.

Note that a scroll container has a very small minimum size - it is
asking to be given whatever space is going spare. That means a window
should be resized, or the scroll placed in a layout that expands it,
otherwise there may be nothing to see. It also means you should not
put a scroll inside a [Box](/container/box) container along the direction it
scrolls, as the box will only offer the minimum size.

The current position is available in the `Offset` field, and
`ScrollToTop()`, `ScrollToBottom()` and `ScrollToOffset(...)` let your
code move the view. The [collection widgets](/collection/list) scroll
internally, so they do not need to be wrapped in this container.

```go
package main

import (
	"fmt"

	"fyne.io/fyne/v2"
	"fyne.io/fyne/v2/app"
	"fyne.io/fyne/v2/container"
	"fyne.io/fyne/v2/widget"
)

func main() {
	myApp := app.New()
	myWindow := myApp.NewWindow("Scroll Container")

	content := container.NewVBox()
	for i := 1; i <= 50; i++ {
		content.Add(widget.NewLabel(fmt.Sprintf("Line %d of some long content", i)))
	}

	scroll := container.NewVScroll(content)

	myWindow.SetContent(scroll)
	myWindow.Resize(fyne.NewSize(300, 200))
	myWindow.ShowAndRun()
}
```
