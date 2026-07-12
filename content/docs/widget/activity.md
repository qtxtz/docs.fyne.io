---
title: Activity

weight: 5180

aliases:
- /widget/activity.html
- /tour/widget/activity
---

The activity widget draws an animated indicator that tells the user
something is happening in the background. Unlike the
[ProgressBar](/widget/progressbar) it does not communicate how much work is left,
so reach for it when the duration of a task is unknown.

Create one with [widget.NewActivity()](/api/v2/widget/activity/#func--newactivity), which takes no
parameters. The animation does not run until you call `Start()`,
and it should be stopped with `Stop()` once the work has completed
so that the app is not animating needlessly.

The indicator will fill the space it is given, so it is common to
place it in a container that keeps it at its minimum size, such as
[container.NewCenter()](/api/v2/container/#func--newcenter). Remember to hide the widget, or replace it
with the results of your work, when the task is done.

```go
package main

import (
	"time"

	"fyne.io/fyne/v2/app"
	"fyne.io/fyne/v2/container"
	"fyne.io/fyne/v2/widget"
)

func main() {
	myApp := app.New()
	myWindow := myApp.NewWindow("Activity Widget")

	activity := widget.NewActivity()
	activity.Start()

	go func() {
		time.Sleep(time.Second * 5) // pretend to do some work
		activity.Stop()
		activity.Hide()
	}()

	myWindow.SetContent(container.NewCenter(activity))
	myWindow.ShowAndRun()
}
```
