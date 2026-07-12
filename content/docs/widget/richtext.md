---
title: RichText

weight: 5100

aliases:
- /widget/richtext.html
- /tour/widget/richtext
---

The rich text widget displays text using many different styles,
and can also include other elements such as images, hyperlinks and
lists. It is the basis of the [Label](/widget/label) widget, which is a
simpler API for the common case of a single run of text.

Content is provided as a list of [widget.RichTextSegment](/api/v2/widget/richtextsegment/#type--richtextsegment) values
passed to [widget.NewRichText()](/api/v2/widget/richtext/#func--newrichtext). The `widget` package includes
segments for text, hyperlinks, images, lists, separators and code
blocks. A [widget.TextSegment](/api/v2/widget/textsegment/#type--textsegment) combines a `Text` string with a
[widget.RichTextStyle](/api/v2/widget/richtextstyle/#type--richtextstyle), and the package provides presets such as
`widget.RichTextStyleHeading` and `widget.RichTextStyleBlockquote`.

Building the segment list by hand is flexible but verbose, so for
most documents it is easier to use [widget.NewRichTextFromMarkdown()](/api/v2/widget/richtext/#func--newrichtextfrommarkdown)
which parses a markdown `string` into the appropriate segments.
You can later call `ParseMarkdown(...)` to replace the content.

By default, a rich text will grow to fit its content - set the
`Wrapping` field (for example to `fyne.TextWrapWord`) and place it
inside a scroll container to display longer documents.

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
	myWindow := myApp.NewWindow("RichText Widget")

	text := widget.NewRichTextFromMarkdown(`
# Rich Text

This paragraph has some *emphasis* and some **strong** words,
as well as a [link](https://fyne.io/).

* it can show lists
* and ` + "`code`" + ` as well`)
	text.Wrapping = fyne.TextWrapWord

	myWindow.SetContent(container.NewScroll(text))
	myWindow.Resize(fyne.NewSize(300, 250))
	myWindow.ShowAndRun()
}
```
