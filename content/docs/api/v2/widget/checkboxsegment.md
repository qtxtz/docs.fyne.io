---
tags: [api]
title: widget.CheckBoxSegment
slug: checkboxsegment

aliases:
- /api/widget/checkboxsegment
- /api/widget/checkboxsegment.html
- /api/v2.0/widget/checkboxsegment
- /api/v2.0/widget/checkboxsegment.html
- /api/v2.1/widget/checkboxsegment
- /api/v2.1/widget/checkboxsegment.html
- /api/v2.2/widget/checkboxsegment
- /api/v2.2/widget/checkboxsegment.html
- /api/v2.3/widget/checkboxsegment
- /api/v2.3/widget/checkboxsegment.html
- /api/v2.4/widget/checkboxsegment
- /api/v2.4/widget/checkboxsegment.html
- /api/v2.5/widget/checkboxsegment
- /api/v2.5/widget/checkboxsegment.html
- /api/v2.6/widget/checkboxsegment
- /api/v2.6/widget/checkboxsegment.html
- /api/v2.7/widget/checkboxsegment
- /api/v2.7/widget/checkboxsegment.html

package: fyne.io/fyne/v2/widget
---


---
```go
import "fyne.io/fyne/v2/widget"
```

## Usage

#### type CheckBoxSegment

```go
type CheckBoxSegment struct {
	Checked bool
	Text    string
}
```

CheckBoxSegment represents checkbox (with text) in a rich text widget.


<div class="since">Since: <code>
2.8</code></div>

#### func (*CheckBoxSegment) Inline

```go
func (c *CheckBoxSegment) Inline() bool
```
Inline returns true as a CheckBoxSegment is usually part of a list item.

#### func (*CheckBoxSegment) Select

```go
func (c *CheckBoxSegment) Select(_, _ fyne.Position)
```
Select does nothing for a checkbox.

#### func (*CheckBoxSegment) SelectedText

```go
func (c *CheckBoxSegment) SelectedText() string
```
SelectedText returns the empty string for a checkbox.

#### func (*CheckBoxSegment) Textual

```go
func (c *CheckBoxSegment) Textual() string
```
Textual returns the content of this segment rendered to plain text.

#### func (*CheckBoxSegment) Unselect

```go
func (c *CheckBoxSegment) Unselect()
```
Unselect does nothing for a checkbox.

#### func (*CheckBoxSegment) Update

```go
func (c *CheckBoxSegment) Update(fyne.CanvasObject)
```
Update doesn't need to change a checkbox

#### func (*CheckBoxSegment) Visual

```go
func (c *CheckBoxSegment) Visual() fyne.CanvasObject
```
Visual returns a new instance of a check widget for this segment.
