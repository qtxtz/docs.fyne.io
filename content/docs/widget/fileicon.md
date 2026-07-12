---
title: FileIcon

weight: 5170

aliases:
- /widget/fileicon.html
- /tour/widget/fileicon
---

The file icon widget shows a graphic that represents a file or a
folder. It inspects the mime type of the item to pick a suitable
icon - such as an image, audio or text symbol - and overlays the
file extension so the user can see the exact format at a glance.

Create one with [widget.NewFileIcon()](/api/v2/widget/fileicon/#func--newfileicon) passing the [fyne.URI](/api/v2/fyne/uri/#type--uri)
of the item to represent. URIs are usually returned from a file
dialog or the [storage](/api/v2/storage/) package, and you can build one from a
path using [storage.NewFileURI()](/api/v2/storage/#func--newfileuri).

Passing `nil` shows a generic file icon, which is useful as a
placeholder before a document has been chosen. Once the user picks
an item you can call `SetURI(...)` to update the display.

```go
package main

import (
	"fyne.io/fyne/v2/app"
	"fyne.io/fyne/v2/container"
	"fyne.io/fyne/v2/storage"
	"fyne.io/fyne/v2/widget"
)

func main() {
	myApp := app.New()
	myWindow := myApp.NewWindow("FileIcon Widget")

	text := widget.NewFileIcon(storage.NewFileURI("./readme.txt"))
	image := widget.NewFileIcon(storage.NewFileURI("./photo.jpg"))

	myWindow.SetContent(container.NewHBox(text, image))
	myWindow.ShowAndRun()
}
```
