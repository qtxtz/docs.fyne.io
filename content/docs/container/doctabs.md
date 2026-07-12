---
title: DocTabs

weight: 4080

aliases:
- /container/doctabs.html
- /tour/container/doctabs
---

The DocTabs container manages a set of open documents, in the way
that a text editor or a web browser presents its tabs. It works much
like [AppTabs](/container/apptabs) - each panel of content is a
[container.TabItem](/api/v2/container/tabitem/#type--tabitem) - but the tabs are designed to come and go as
the user works, so each one includes a close button and the bar will
scroll when there are more tabs than fit.

Create the container with `container.NewDocTabs(...)`, passing any
items that should be open to begin with. `Append(...)` and
`Remove(...)` change the list later.

The behavior is driven by callbacks. Set `CreateTab` to a function
returning a new `*TabItem` and the container will show a "+" button
that lets the user open a document. `OnSelected` and `OnClosed` tell
you when the user switches or closes a tab. If a document has unsaved
changes you can set `CloseIntercept` - when that is set the tab is
*not* closed automatically, instead your function is called and it is
up to you to prompt the user and call `Remove(...)` if they confirm.

As with AppTabs, `SetTabLocation(...)` moves the bar to another edge.

```go
package main

import (
	"fmt"

	"fyne.io/fyne/v2"
	"fyne.io/fyne/v2/app"
	"fyne.io/fyne/v2/container"
	"fyne.io/fyne/v2/widget"
)

func main() {
	myApp := app.New()
	myWindow := myApp.NewWindow("DocTabs Container")

	count := 2
	tabs := container.NewDocTabs(
		container.NewTabItem("Doc 1", widget.NewLabel("Content of document 1")),
		container.NewTabItem("Doc 2", widget.NewLabel("Content of document 2")),
	)

	tabs.CreateTab = func() *container.TabItem {
		count++
		return container.NewTabItem(fmt.Sprintf("Doc %d", count),
			widget.NewLabel(fmt.Sprintf("Content of document %d", count)))
	}

	myWindow.SetContent(tabs)
	myWindow.Resize(fyne.NewSize(400, 300))
	myWindow.ShowAndRun()
}
```
