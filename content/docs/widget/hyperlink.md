---
title: Hyperlink

weight: 5090

aliases:
- /widget/hyperlink.html
- /tour/widget/hyperlink
---

The hyperlink widget shows a piece of text that, when tapped,
opens a web address in the user's default browser.
It is created with [widget.NewHyperlink()](/api/v2/widget/hyperlink/#func--newhyperlink) which takes the
`string` to display and a `*url.URL` for the destination.
As the standard library `url.Parse(...)` returns an error you may
prefer to build the address once and handle the failure, as in
the example below.

If you need to control the appearance of the text you can use
[widget.NewHyperlinkWithStyle()](/api/v2/widget/hyperlink/#func--newhyperlinkwithstyle) which adds a [fyne.TextAlign](/api/v2/fyne/textalign/#type--textalign)
and a [fyne.TextStyle](/api/v2/fyne/textstyle/#type--textstyle) parameter.

The `URL` field can be set at any time to change where the link
points, and setting the `OnTapped` function replaces the default
"open in browser" behavior if you want to handle the tap yourself.

```go
package main

import (
	"net/url"

	"fyne.io/fyne/v2"
	"fyne.io/fyne/v2/app"
	"fyne.io/fyne/v2/widget"
)

func main() {
	myApp := app.New()
	myWindow := myApp.NewWindow("Hyperlink Widget")

	link, err := url.Parse("https://fyne.io/")
	if err != nil {
		fyne.LogError("Could not parse URL", err)
	}

	myWindow.SetContent(widget.NewHyperlink("Fyne website", link))
	myWindow.ShowAndRun()
}
```
