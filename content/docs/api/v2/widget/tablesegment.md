---
tags: [api]
title: widget.TableSegment
slug: tablesegment

aliases:
- /api/widget/tablesegment
- /api/widget/tablesegment.html
- /api/v2.0/widget/tablesegment
- /api/v2.0/widget/tablesegment.html
- /api/v2.1/widget/tablesegment
- /api/v2.1/widget/tablesegment.html
- /api/v2.2/widget/tablesegment
- /api/v2.2/widget/tablesegment.html
- /api/v2.3/widget/tablesegment
- /api/v2.3/widget/tablesegment.html
- /api/v2.4/widget/tablesegment
- /api/v2.4/widget/tablesegment.html
- /api/v2.5/widget/tablesegment
- /api/v2.5/widget/tablesegment.html
- /api/v2.6/widget/tablesegment
- /api/v2.6/widget/tablesegment.html
- /api/v2.7/widget/tablesegment
- /api/v2.7/widget/tablesegment.html

package: fyne.io/fyne/v2/widget
---


---
```go
import "fyne.io/fyne/v2/widget"
```

## Usage

#### type TableSegment

```go
type TableSegment struct {
	// Headers holds the cells of the header row, or nil for a header-less table.
	Headers [][]RichTextSegment
	// Rows holds the body rows; each row is a slice of cells, each cell a slice of segments.
	Rows       [][][]RichTextSegment
	Alignments []fyne.TextAlign
}
```

TableSegment represents a table within a rich text widget.


<div class="since">Since: <code>
2.8</code></div>

#### func (*TableSegment) Inline

```go
func (t *TableSegment) Inline() bool
```
Inline returns false as a table is a full-width block element.

#### func (*TableSegment) Select

```go
func (t *TableSegment) Select(_, _ fyne.Position)
```
Select does nothing for a table.

#### func (*TableSegment) SelectedText

```go
func (t *TableSegment) SelectedText() string
```
SelectedText returns the table content as text.

#### func (*TableSegment) Textual

```go
func (t *TableSegment) Textual() string
```
Textual returns the table content as tab-separated, newline-delimited text.

#### func (*TableSegment) Unselect

```go
func (t *TableSegment) Unselect()
```
Unselect does nothing for a table.

#### func (*TableSegment) Update

```go
func (t *TableSegment) Update(fyne.CanvasObject)
```
Update does nothing; a table visual is rebuilt rather than updated.

#### func (*TableSegment) Visual

```go
func (t *TableSegment) Visual() fyne.CanvasObject
```
Visual returns a new grid laying out the table cells.
