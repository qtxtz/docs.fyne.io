---
tags: [api]
title: widget.CodeBlockSegment
slug: codeblocksegment

aliases:
- /api/widget/codeblocksegment
- /api/widget/codeblocksegment.html
- /api/v2.0/widget/codeblocksegment
- /api/v2.0/widget/codeblocksegment.html
- /api/v2.1/widget/codeblocksegment
- /api/v2.1/widget/codeblocksegment.html
- /api/v2.2/widget/codeblocksegment
- /api/v2.2/widget/codeblocksegment.html
- /api/v2.3/widget/codeblocksegment
- /api/v2.3/widget/codeblocksegment.html
- /api/v2.4/widget/codeblocksegment
- /api/v2.4/widget/codeblocksegment.html
- /api/v2.5/widget/codeblocksegment
- /api/v2.5/widget/codeblocksegment.html
- /api/v2.6/widget/codeblocksegment
- /api/v2.6/widget/codeblocksegment.html
- /api/v2.7/widget/codeblocksegment
- /api/v2.7/widget/codeblocksegment.html

package: fyne.io/fyne/v2/widget
---


---
```go
import "fyne.io/fyne/v2/widget"
```

## Usage

#### type CodeBlockSegment

```go
type CodeBlockSegment struct {
	Text string
}
```

CodeBlockSegment represents a fenced or indented code block. It renders its content as monospace text on a panel, so the block stands apart from the surrounding prose.


<div class="since">Since: <code>
2.8</code></div>

#### func (*CodeBlockSegment) Inline

```go
func (c *CodeBlockSegment) Inline() bool
```
Inline returns false as a code block is a full-width block element.

#### func (*CodeBlockSegment) Select

```go
func (c *CodeBlockSegment) Select(_, _ fyne.Position)
```
Select does nothing for a code block.

#### func (*CodeBlockSegment) SelectedText

```go
func (c *CodeBlockSegment) SelectedText() string
```
SelectedText returns the code block content.

#### func (*CodeBlockSegment) Textual

```go
func (c *CodeBlockSegment) Textual() string
```
Textual returns the raw content of this code block.

#### func (*CodeBlockSegment) Unselect

```go
func (c *CodeBlockSegment) Unselect()
```
Unselect does nothing for a code block.

#### func (*CodeBlockSegment) Update

```go
func (c *CodeBlockSegment) Update(o fyne.CanvasObject)
```
Update applies the current content of this segment to an existing visual.

#### func (*CodeBlockSegment) Visual

```go
func (c *CodeBlockSegment) Visual() fyne.CanvasObject
```
Visual returns a new panel widget rendering this code block.
