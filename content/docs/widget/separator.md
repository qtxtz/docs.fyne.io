---
title: Separator

weight: 5140

aliases:
- /widget/separator.html
- /tour/widget/separator
---

The separator widget draws a thin dividing line that helps to
visually group the elements around it. It is created with
[widget.NewSeparator()](/api/v2/widget/separator/#func--newseparator) and takes no parameters - the colour and
thickness both come from the current theme.

A separator has no preferred direction, instead it fills the space
that the layout gives it. In a [container.NewVBox()](/api/v2/container/#func--newvbox) it will draw a
horizontal line between the items above and below, and in a
[container.NewHBox()](/api/v2/container/#func--newhbox) it will draw a vertical line instead.

If you want a divider that the user can drag to resize the content
on either side then use the [Split](/api/container/split) container rather than a
separator.

```go
package main

import (
	"fyne.io/fyne/v2/app"
	"fyne.io/fyne/v2/container"
	"fyne.io/fyne/v2/widget"
)

func main() {
	myApp := app.New()
	myWindow := myApp.NewWindow("Separator Widget")

	content := container.NewVBox(
		widget.NewLabel("Above the line"),
		widget.NewSeparator(),
		widget.NewLabel("Below the line"),
	)

	myWindow.SetContent(content)
	myWindow.ShowAndRun()
}
```
