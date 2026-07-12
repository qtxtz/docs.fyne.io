---
title: Slider

weight: 5150

aliases:
- /widget/slider.html
- /tour/widget/slider
---

The slider widget allows a user to choose a number by dragging a
handle between two fixed values. Create one using
[widget.NewSlider()](/api/v2/widget/slider/#func--newslider) which takes the `float64` minimum and
maximum of the range. Read the chosen number from the `Value`
field, or set it to move the handle from your code.

The `Step` field controls how far the handle moves at a time, it
defaults to `1` so remember to set a smaller value if you want a
fine-grained range such as 0 to 1. To lay the widget out vertically
set the `Orientation` field to `widget.Vertical`.

Two callbacks are available. `OnChanged` is called for every value
the slider passes through as the user drags, which is useful for
live previews. `OnChangeEnded` is called once the user releases the
handle, which is a better place to trigger anything expensive.

A slider can also be connected to a [data binding](/binding/) using
[widget.NewSliderWithData()](/api/v2/widget/slider/#func--newsliderwithdata), passing a `binding.Float`.

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
	myWindow := myApp.NewWindow("Slider Widget")

	slide := widget.NewSlider(0, 100)
	slide.Step = 5
	slide.OnChangeEnded = func(value float64) {
		log.Println("Slider set to", value)
	}

	myWindow.SetContent(slide)
	myWindow.Resize(fyne.NewSize(200, 100))
	myWindow.ShowAndRun()
}
```
