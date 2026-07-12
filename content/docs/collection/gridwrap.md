---
title: GridWrap

weight: 6040

aliases:
- /collection/gridwrap.html
- /widget/gridwrap
---

The `GridWrap` collection widget lays items out at a fixed size and
wraps them onto as many rows as are needed, scrolling vertically when
there are more than will fit. Think of a photo browser or an icon
view - as the window gets wider more items fit on each row.

Like the [List](/collection/list), [Table](/collection/table) and [Tree](/collection/tree) widgets it is designed to
present large amounts of data efficiently, so it does not hold your
items directly. Instead it uses callbacks to ask for data only for
the cells that are currently visible, re-using the widgets as the
user scrolls.

The API matches `List` closely. [widget.NewGridWrap()](/api/v2/widget/gridwrap/#func--newgridwrap) takes three
callbacks: `Length` returns how many items there are, `CreateItem`
returns a new template object, and `UpdateItem` applies the data for
a given `GridWrapItemID` to one of those templates. Because every
cell is the same size, the minimum size of the object returned by
`CreateItem` determines the size of each item in the grid.

Set `OnSelected` to be told when the user taps an item. As with the
other collection widgets you can bind the content to a data list
using [widget.NewGridWrapWithData()](/api/v2/widget/gridwrap/#func--newgridwrapwithdata).

Do not confuse this with the [grid wrap layout](/container/gridwrap), which
arranges a fixed set of items in the same pattern but without the
caching that makes this widget suitable for large data.

```go
package main

import (
	"fmt"

	"fyne.io/fyne/v2"
	"fyne.io/fyne/v2/app"
	"fyne.io/fyne/v2/widget"
)

func main() {
	myApp := app.New()
	myWindow := myApp.NewWindow("GridWrap Widget")

	var data []string
	for i := 1; i <= 100; i++ {
		data = append(data, fmt.Sprintf("Item\n%d", i))
	}

	grid := widget.NewGridWrap(
		func() int {
			return len(data)
		},
		func() fyne.CanvasObject {
			return widget.NewLabel("temp\nlate")
		},
		func(id widget.GridWrapItemID, item fyne.CanvasObject) {
			item.(*widget.Label).SetText(data[id])
		})

	myWindow.SetContent(grid)
	myWindow.Resize(fyne.NewSize(400, 300))
	myWindow.ShowAndRun()
}
```
