---
title: Navigation

weight: 4120

aliases:
- /container/navigation.html
---

The Navigation container provides a stack based navigation, the
pattern that mobile apps use to drill down into detail and then step
back out again. It shows a bar with a back button and a title above
the content, and only the most recent item in the stack is visible.

Create one using `container.NewNavigation(...)` with the root
[fyne.CanvasObject](/api/v2/fyne/canvasobject/#type--canvasobject) - the screen the user starts on and can never
go back beyond. `container.NewNavigationWithTitle(...)` also sets the
default title for the bar.

To move forward call `Push(...)` with the content of the new screen,
or `PushWithTitle(...)` to give that screen its own title in the bar.
The user can return using the back button, and your code can do the
same by calling `Back()`. Because the stack is kept, `Forward()` will
return to a screen the user has stepped back from.

The `OnBack` and `OnForward` fields are called when the user taps
those controls. They default to performing the navigation, so replace
them only if you need to intercept the move - remember to call
`Back()` or `Forward()` yourself if the move should still happen.

Added in Fyne 2.7.

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
	myWindow := myApp.NewWindow("Navigation Container")

	var nav *container.Navigation
	root := container.NewVBox(
		widget.NewLabel("The first screen"),
		widget.NewButton("Show detail", func() {
			detail := widget.NewLabel("The detail of the item")
			nav.PushWithTitle(detail, "Detail")
		}),
	)

	nav = container.NewNavigationWithTitle(root, "Home")

	myWindow.SetContent(nav)
	myWindow.Resize(fyne.NewSize(300, 200))
	myWindow.ShowAndRun()
}
```
