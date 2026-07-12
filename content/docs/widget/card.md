---
title: Card

weight: 5120

aliases:
- /widget/card.html
- /tour/widget/card
---

The card widget groups related information together, drawing a
raised panel with an optional title, subtitle, image and content.
Use [widget.NewCard()](/api/v2/widget/card/#func--newcard) passing the `Title` and `SubTitle`
strings along with the [fyne.CanvasObject](/api/v2/fyne/canvasobject/#type--canvasobject) that should be shown
in the body of the card.

Every part of a card is optional, so passing "" for either of the
text values, or `nil` for the content, will simply omit that
element. This makes the card useful as a simple bordered panel as
well as a full header and content group.

An image can be added by setting the `Image` field to a
[canvas.Image](/api/v2/canvas/image/#type--image). It will be displayed across the top of the card,
above the title.

```go
package main

import (
	"fyne.io/fyne/v2/app"
	"fyne.io/fyne/v2/widget"
)

func main() {
	myApp := app.New()
	myWindow := myApp.NewWindow("Card Widget")

	content := widget.NewLabel("Card content can be any widget or container")
	card := widget.NewCard("Card title", "with a subtitle", content)

	myWindow.SetContent(card)
	myWindow.ShowAndRun()
}
```
