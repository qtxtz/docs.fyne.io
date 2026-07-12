---
title: PopUp

weight: 5190

aliases:
- /widget/popup.html
- /tour/widget/popup
---

The pop-up widget floats a small piece of content above the rest of
your app. Because it is drawn over everything else it is added to a
[fyne.Canvas](/api/v2/fyne/canvas/#type--canvas) rather than to a container, so each constructor
takes the canvas of the window it should appear in.

The simplest approach is [widget.ShowPopUp()](/api/v2/widget/popup/#func--showpopup), which creates the
pop-up and displays it immediately at the centre of the canvas.
Use [widget.ShowPopUpAtPosition()](/api/v2/widget/popup/#func--showpopupatposition) if you want to specify where it
appears, for example next to the widget that was tapped. Tapping
elsewhere will dismiss the pop-up, or you can call `Hide()` on it.

If the user must respond before continuing then create a modal pop
up using [widget.NewModalPopUp()](/api/v2/widget/popup/#func--newmodalpopup) - this dims the app behind it and
will not be dismissed by a tap outside, so your content needs to
provide a way to close it. For standard messages and confirmations
the [dialog](/api/v2/dialog/) package is built on this and is usually a better
choice.

A common use of pop-ups is to display a menu. Pass a [fyne.Menu](/api/v2/fyne/menu/#type--menu)
to [widget.ShowPopUpMenuAtPosition()](/api/v2/widget/popupmenu/#func--showpopupmenuatposition) to show a standard menu at
the requested location.

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
	myWindow := myApp.NewWindow("PopUp Widget")

	var popUp *widget.PopUp
	content := container.NewVBox(
		widget.NewLabel("Content of the pop up"),
		widget.NewButton("Close", func() {
			popUp.Hide()
		}),
	)
	popUp = widget.NewModalPopUp(content, myWindow.Canvas())

	open := widget.NewButton("Show pop up", func() {
		popUp.Show()
	})

	myWindow.SetContent(container.NewCenter(open))
	myWindow.Resize(fyne.NewSize(300, 200))
	myWindow.ShowAndRun()
}
```
