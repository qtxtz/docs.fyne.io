---
title: SelectEntry

weight: 5160

aliases:
- /widget/selectentry.html
- /tour/widget/selectentry
---

The select entry widget combines the [Entry](/widget/entry) and the select
widget described in [Choices](/widget/choices). The user can pick one of the
values you offer from a drop-down list, or they can ignore the list
and type a value of their own.

Construct one with [widget.NewSelectEntry()](/api/v2/widget/selectentry/#func--newselectentry), passing a slice of
`string` for the options that should be suggested. The list can be
replaced later using `SetOptions(...)`.

Because a select entry extends the entry widget you use it in the
same way - read the `Text` field for the current value and set
`OnChanged` to be told when it changes, whether the user typed the
text or chose it from the list. Fields like `PlaceHolder` and
`Validator` work as they do for a regular entry.

```go
package main

import (
	"log"

	"fyne.io/fyne/v2"
	"fyne.io/fyne/v2/app"
	"fyne.io/fyne/v2/widget"
)

func main() {
	myApp := app.New()
	myWindow := myApp.NewWindow("SelectEntry Widget")

	combo := widget.NewSelectEntry([]string{"Red", "Green", "Blue"})
	combo.PlaceHolder = "Choose or type a colour"
	combo.OnChanged = func(value string) {
		log.Println("Colour is", value)
	}

	myWindow.SetContent(combo)
	myWindow.Resize(fyne.NewSize(250, 100))
	myWindow.ShowAndRun()
}
```
