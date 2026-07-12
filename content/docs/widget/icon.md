---
title: Icon

weight: 5080

aliases:
- /widget/icon.html
- /tour/widget/icon
---

The icon widget draws a single image resource, scaled to fit the
space available and coloured to match the current theme.
It is created using [widget.NewIcon()](/api/v2/widget/icon/#func--newicon) which takes a
[fyne.Resource](/api/v2/fyne/resource/#type--resource) parameter for the image data to display.

The icons in the `theme` package are the usual source of this
resource, they are designed to adapt when the user switches
between light and dark themes. If you want to show your own
artwork then load it as a resource, using helpers such as
[fyne.LoadResourceFromPath()](/api/v2/fyne/resource/#func--loadresourcefrompath), though bundling the file into your
app is recommended where possible.

An icon can be updated later by calling `SetResource(...)` with
a new resource. If you want to display a photograph or another
image that should not be themed, use [canvas.Image](/api/v2/canvas/image/#type--image) instead.

```go
package main

import (
	"fyne.io/fyne/v2/app"
	"fyne.io/fyne/v2/container"
	"fyne.io/fyne/v2/theme"
	"fyne.io/fyne/v2/widget"
)

func main() {
	myApp := app.New()
	myWindow := myApp.NewWindow("Icon Widget")

	home := widget.NewIcon(theme.HomeIcon())
	info := widget.NewIcon(theme.InfoIcon())

	myWindow.SetContent(container.NewVBox(home, info))
	myWindow.ShowAndRun()
}
```
