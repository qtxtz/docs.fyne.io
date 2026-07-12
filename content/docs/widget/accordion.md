---
title: Accordion

weight: 5130

aliases:
- /widget/accordion.html
- /tour/widget/accordion
---

The accordion widget presents a vertical list of headings, each of
which can be tapped to reveal the detail that it contains. It is a
good way to fit many sections of content into a small space, as the
user only opens the one they are interested in.

Each section is a [widget.AccordionItem](/api/v2/widget/accordionitem/#type--accordionitem), created with
[widget.NewAccordionItem()](/api/v2/widget/accordionitem/#func--newaccordionitem) which takes the `string` title and the
[fyne.CanvasObject](/api/v2/fyne/canvasobject/#type--canvasobject) that should be revealed when it is opened.
Pass as many items as you wish to [widget.NewAccordion()](/api/v2/widget/accordion/#func--newaccordion), or use
the `Append(...)` and `Remove(...)` methods to change the list later.

By default only one item can be open at a time - opening a new
section will close the previous one. Set the `MultiOpen` field to
`true` if you would rather that many sections can be open together.
The `Open(...)`, `Close(...)` and `CloseAll()` methods allow your
code to control which sections are showing.

```go
package main

import (
	"fyne.io/fyne/v2"
	"fyne.io/fyne/v2/app"
	"fyne.io/fyne/v2/widget"
)

func main() {
	myApp := app.New()
	myWindow := myApp.NewWindow("Accordion Widget")

	accordion := widget.NewAccordion(
		widget.NewAccordionItem("Details", widget.NewLabel("Information about this item")),
		widget.NewAccordionItem("Settings", widget.NewCheck("Enabled", func(bool) {})),
	)
	accordion.Open(0)

	myWindow.SetContent(accordion)
	myWindow.Resize(fyne.NewSize(300, 200))
	myWindow.ShowAndRun()
}
```
